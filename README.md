# Agricultural-chatbot
import streamlit as st
import faiss
import numpy as np
from sentence_transformers import SentenceTransformer
import openai
import fitz

openai.api_key = "YOUR_OPENAI_API_KEY"

embed_model = SentenceTransformer('sentence-transformers/all-MiniLM-L6-v2')

def extract_text_from_pdf(pdf_file):
    doc = fitz.open(stream=pdf_file.read(), filetype="pdf")
    text = ""
    for page in doc:
        text += page.get_text()
    return text

def chunk_text(text, max_len=500):
    sentences = text.split('. ')
    chunks = []
    current = ""
    for s in sentences:
        if len(current) + len(s) < max_len:
            current += s + '. '
        else:
            chunks.append(current.strip())
            current = s + '. '
    if current:
        chunks.append(current.strip())
    return chunks

def build_faiss_index(chunks):
    vectors = embed_model.encode(chunks)
    dim = vectors.shape[1]
    index = faiss.IndexFlatL2(dim)
    index.add(np.array(vectors).astype('float32'))
    return index

@st.cache_data(show_spinner=False)
def retrieve_context(query, index, chunks, top_k=5):
    q_vec = embed_model.encode([query])
    D, I = index.search(np.array(q_vec).astype('float32'), top_k)
    return [chunks[i] for i in I[0]]

def ask_gpt4(question, context, history):
    conversation = []
    for q,a in history:
        conversation.append({"role": "user", "content": q})
        conversation.append({"role": "assistant", "content": a})
    prompt = f"Use the context below to answer the question.\n\nContext:\n{context}\n\nQuestion:\n{question}\n\nAnswer:"
    conversation.append({"role": "user", "content": prompt})
    resp = openai.ChatCompletion.create(
        model="gpt-4",
        messages=conversation,
        temperature=0.7,
        max_tokens=500
    )
    return resp.choices[0].message.content.strip()

st.set_page_config(page_title="Agri Advice Chatbot", page_icon="🌾")

st.title("Agricultural Advice Chatbot")

if "knowledge_chunks" not in st.session_state:
    st.session_state.knowledge_chunks = []
    st.session_state.knowledge_index = None
    st.session_state.chat_history = []

uploaded_files = st.file_uploader("Upload Agricultural PDF documents", type="pdf", accept_multiple_files=True)

if uploaded_files:
    all_text = ""
    with st.spinner(f"Processing {len(uploaded_files)} document(s)..."):
        for file in uploaded_files:
            text = extract_text_from_pdf(file)
            all_text += text + "\n\n"
        chunks = chunk_text(all_text)
        st.session_state.knowledge_chunks = chunks
        st.session_state.knowledge_index = build_faiss_index(chunks)
    st.success(f"Knowledge base created from {len(uploaded_files)} PDFs with {len(chunks)} chunks!")

query = st.text_input("Enter your agricultural question:")

if query:
    if st.session_state.knowledge_index is None or len(st.session_state.knowledge_chunks) == 0:
        st.warning("Please upload at least one agricultural document first.")
    else:
        context_chunks = retrieve_context(query, st.session_state.knowledge_index, st.session_state.knowledge_chunks)
        combined_context = "\n\n".join(context_chunks)

        try:
            answer = ask_gpt4(query, combined_context, st.session_state.chat_history)
        except Exception:
            answer = "Sorry, I am unable to answer at the moment."

        st.session_state.chat_history.append((query, answer))

        st.markdown("### Response:")
        st.write(answer)

if st.button("Clear Chat"):
    st.session_state.chat_history = []
