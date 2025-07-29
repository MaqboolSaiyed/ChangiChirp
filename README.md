# 🛫 Changi & Jewel RAG Chatbot

Welcome to the **Changi Airport RAG Chatbot**! ✈️

Ever wondered about the best places to nap at Changi? Or where to find the most Instagrammable spots in Jewel? This chatbot is your AI-powered travel buddy, ready to answer all your questions about Changi Airport and Jewel Changi using the latest in Retrieval-Augmented Generation (RAG) and Large Language Models (LLMs).

---

## 🚀 What Does It Do?
- **Answers your questions** about Changi Airport & Jewel Changi using real, up-to-date info
- **Retrieves facts** from a custom-built knowledge base (no hallucinations here!)
- **Uses 3 LLMs** for accuracy, fallback, and response improvement
- **Fun, fast, and friendly** – just like Changi itself!

---

## 🧠 How It Works
1. **You ask a question** ("Where can I find free rest areas?")
2. The chatbot **retrieves relevant documents** from a FAISS vector database
3. It uses a **primary LLM** (Mistral) to generate an answer
4. If the answer isn’t good enough, it **falls back** to a secondary LLM (Llama2)
5. For extra polish, a **third LLM** (Mistral) can improve the response
6. You get a **clear, concise, and helpful answer** – with sources!

---

## 🏗️ Tech Stack
- **FastAPI** – Blazing fast Python web framework
- **LangChain** – Orchestrates retrieval and LLMs
- **Ollama** – Local LLM serving (Mistral, Llama2, all-minilm)
- **FAISS** – Lightning-fast vector search
- **Jinja2** – For templating (if you want to get fancy)

---

## 🛠️ Getting Started
1. **Clone this repo**
2. **Install dependencies**: `pip install -r requirements.txt`
3. **Ingest data**: `python ingest.py` (builds the FAISS index)
4. **Run the server**: `uvicorn main:app --reload`
5. **Open your browser**: [http://localhost:8000/chat-ui](http://localhost:8000/chat-ui)

---

## 🤖 Example Questions
- "What are the best food options in Jewel?"
- "Is there a free movie theater at Changi?"
- "How do I get from Terminal 1 to Jewel?"

---

## 🧩 Project Structure
```
ChatBot_Ollama/
├── main.py         # FastAPI app & core logic
├── ingest.py       # Data ingestion & FAISS index builder
├── faiss_index/    # Vector DB files
├── static/         # Frontend (HTML/JS)
├── requirements.txt
├── README.md       # (You are here!)
```

---

## 💡 Why So Many Models?
- **Primary LLM**: Fast, accurate answers
- **Fallback LLM**: Catches edge cases & failures
- **Summarizer LLM**: Makes responses friendlier

---

## 🐞 Troubleshooting
- **Index not found?** Run `python ingest.py` first!
- **Model mismatch?** Make sure the embedding model matches the one used for the index.
- **Still stuck?** Check the logs for detailed error messages.

---

## 🌏 About Changi & Jewel
This project is not affiliated with Changi Airport Group. It’s a fun, open-source experiment to make travel info more accessible and interactive!

---

## 📬 Contributing
Pull requests, issues, and feedback are welcome! Let’s make travel smarter, together.

---

## 🦄 Enjoy your journey – and happy chatting! 🦄
