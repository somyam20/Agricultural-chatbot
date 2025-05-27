PS C:\Users\somya.misra\Downloads\Sentiment-analysis-main> streamlit run "C:\Users\somya.misra\Downloads\Sentiment-analysis-main\Sentiment-analysis-main\agriculturechatbot.py"

  You can now view your Streamlit app in your browser.

  Local URL: http://localhost:8501
  Network URL: http://10.4.8.204:8501

C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\requests\__init__.py:86: 
RequestsDependencyWarning: Unable to find acceptable character detection dependency (chardet or charset_normalizer).
  warnings.warn(
modules.json: 100%|█████████████████████████████████████████████████████████████| 349/349 [00:00<?, ?B/s]
C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\huggingface_hub\file_download.py:143: UserWarning: `huggingface_hub` cache-system uses symlinks by default to efficiently store duplicated files but your machine does not support them in C:\Users\somya.misra\.cache\huggingface\hub\models--sentence-transformers--all-MiniLM-L6-v2. Caching files will still work but in a degraded version that might require more space on your disk. This warning can be disabled by setting the `HF_HUB_DISABLE_SYMLINKS_WARNING` environment variable. For more details, see https://huggingface.co/docs/huggingface_hub/how-to-cache#limitations.
To support symlinks on Windows, you either need to activate Developer Mode or to run Python as an administrator. In order to activate developer mode, see this article: https://docs.microsoft.com/en-us/windows/apps/get-started/enable-your-device-for-development
  warnings.warn(message)
config_sentence_transformers.json: 100%|████████████████████████████████████████| 116/116 [00:00<?, ?B/s]
README.md: 100%|████████████████████████████████████████████████████| 10.5k/10.5k [00:00<00:00, 10.5MB/s]
sentence_bert_config.json: 100%|██████████████████████████████████████████████| 53.0/53.0 [00:00<?, ?B/s]
config.json: 100%|██████████████████████████████████████████████████████████████| 612/612 [00:00<?, ?B/s]
Xet Storage is enabled for this repo, but the 'hf_xet' package is not installed. Falling back to regular HTTP download. For better performance, install the package with: `pip install huggingface_hub[hf_xet]` or `pip install hf_xet`
model.safetensors: 100%|████████████████████████████████████████████| 90.9M/90.9M [00:07<00:00, 11.9MB/s]
tokenizer_config.json: 100%|████████████████████████████████████████████████████| 350/350 [00:00<?, ?B/s]
vocab.txt: 100%|███████████████████████████████████████████████████████| 232k/232k [00:00<00:00, 576kB/s]
tokenizer.json: 100%|█████████████████████████████████████████████████| 466k/466k [00:00<00:00, 1.20MB/s]
special_tokens_map.json: 100%|██████████████████████████████████████████████████| 112/112 [00:00<?, ?B/s]
config.json: 100%|███████████████████████████████████████████████████████| 190/190 [00:00<00:00, 198kB/s]
2025-05-27 10:13:45.807 Examining the path of torch.classes raised:
Traceback (most recent call last):
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\web\bootstrap.py", line 347, in run
    if asyncio.get_running_loop().is_running():
       ^^^^^^^^^^^^^^^^^^^^^^^^^^
RuntimeError: no running event loop

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\watcher\local_sources_watcher.py", line 217, in get_module_paths
    potential_paths = extract_paths(module)
                      ^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\watcher\local_sources_watcher.py", line 210, in <lambda>
    lambda m: list(m.__path__._path),
                   ^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\torch\_classes.py", line 13, in __getattr__
    proxy = torch._C._get_custom_class_python_wrapper(self.name, attr)
            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
RuntimeError: Tried to instantiate class '__path__._path', but it does not exist! Ensure that it is registered via torch::class_
2025-05-27 10:32:47.660 Uncaught app execution
Traceback (most recent call last):
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 625, in _to_bytes
    reduce_data = obj.__reduce__()
                  ^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\copyreg.py", line 90, in _reduce_ex
    dict = getstate()
           ^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\faiss\class_wrappers.py", line 824, in index_getstate
    return {"this": faiss.serialize_index(self).tobytes()}
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\faiss\__init__.py", line 332, in 
serialize_index
    return vector_to_array(writer.data)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\faiss\array_conversions.py", line 116, in vector_to_array
    assert classname.endswith('Vector')
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
AssertionError

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\cache_utils.py", line 450, in _make_value_key
    update_hash(
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 162, in update_hash
    ch.update(hasher, val)
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 345, in update
    b = self.to_bytes(obj)
        ^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 327, in to_bytes
    b = b"%s:%s" % (tname, self._to_bytes(obj))
                           ^^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 627, in _to_bytes
    raise UnhashableTypeError() from ex
streamlit.runtime.caching.cache_errors.UnhashableTypeError

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\scriptrunner\exec_code.py", line 121, in exec_func_with_error_handling
    result = func()
             ^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\scriptrunner\script_runner.py", line 645, in code_to_exec
    exec(code, module.__dict__)
  File "C:\Users\somya.misra\Downloads\Sentiment-analysis-main\Sentiment-analysis-main\agriculturechatbot.py", line 104, in <module>
    context_chunks = retrieve_context(query, st.session_state.knowledge_index, st.session_state.knowledge_chunks)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\cache_utils.py", line 219, in __call__
    return self._get_or_create_cached_value(args, kwargs, spinner_message)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\cache_utils.py", line 234, in _get_or_create_cached_value
    value_key = _make_value_key(
                ^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\cache_utils.py", line 458, in _make_value_key
    raise UnhashableParamError(cache_type, func, arg_name, arg_value, exc)
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\cache_utils.py", line 450, in _make_value_key
    update_hash(
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 162, in update_hash
    ch.update(hasher, val)
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 345, in update
    b = self.to_bytes(obj)
        ^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 327, in to_bytes
    b = b"%s:%s" % (tname, self._to_bytes(obj))
                           ^^^^^^^^^^^^^^^^^^^
  File "C:\Users\somya.misra\AppData\Local\anaconda3\envs\streamlitenv\Lib\site-packages\streamlit\runtime\caching\hashing.py", line 627, in _to_bytes
    raise UnhashableTypeError() from ex
streamlit.runtime.caching.cache_errors.UnhashableParamError: Cannot hash argument 'index' (of type `faiss.swigfaiss_avx2.IndexFlatL2`) in 'retrieve_context'.

To address this, you can tell Streamlit not to hash this argument by adding a
leading underscore to the argument's name in the function signature:

```
@st.cache_data
def retrieve_context(_index, ...):
    ...
```
