# 🐞 Issues & Solutions: Changi RAG Chatbot

Welcome to the behind-the-scenes troubleshooting log! Here’s a candid look at the bumps, bugs, and brilliant fixes that shaped this project.

---

## 🚩 Problem Statements & Solutions

### 1. FAISS Indexing Not Working
**Problem:**
- FAISS index failed to load or deserialize, especially after changing embedding models.
- Error: `Error loading FAISS index: ...` or `Index not found at faiss_index`.

**Solution:**
- Always use the same embedding model for both index creation and querying.
- If the index is corrupted or mismatched, delete the `faiss_index/` folder and rerun `python ingest.py`.
- Added error handling to auto-delete and prompt for re-ingestion if loading fails.

---

### 2. Model Unable to Access Vector DB
**Problem:**
- LLMs or retrievers couldn’t access the FAISS vector store, leading to empty or irrelevant results.

**Solution:**
- Ensured correct path and permissions for `faiss_index/`.
- Added diagnostics to print vector count, dimensions, and sample vectors at startup.
- Provided clear error messages and troubleshooting steps in logs.

---

### 3. Multi-Model Setup for Better Responses
**Problem:**
- Single LLM sometimes gave low-quality or generic answers.
- Needed fallback and response improvement for reliability.

**Solution:**
- Integrated three models:
  - **Primary LLM (Mistral):** Fast, accurate answers
  - **Fallback LLM (Llama2):** Handles failures or low-quality responses
  - **Summarizer LLM (Mistral):** Improves answer clarity and friendliness
- Implemented quality checks and fallback logic in the API.

---

### 4. Data Retrieval Issues
**Problem:**
- Sometimes, no documents were retrieved for a query (empty context).

**Solution:**
- Used both MMR and similarity retrievers, then deduplicated results.
- Added logging to debug retrieval failures and suggest fixes.

---

### 5. General Debugging & Logging
**Problem:**
- Hard to trace errors in a multi-component system.

**Solution:**
- Added detailed print/log statements at every major step (embedding, retrieval, LLM calls, etc.).
- Provided user-friendly error messages in the API and UI.

---

## 💡 Lessons Learned
- Always match your embedding model between ingestion and querying!
- Multi-model setups boost reliability and user experience.
- Good logging saves hours of debugging.

---

## 🛠️ For Future Developers
- If you hit a wall, check the logs first.
- Don’t be afraid to delete and rebuild the index.
- Experiment with different models and retrievers for best results.

---

Happy hacking! 🚀 