# 🧠 AI Chatbot with LangChain, OpenAI, and Pinecone

An intelligent, context-aware chatbot built with Python using **LangChain**, **OpenAI**, and **Pinecone** for semantic search and conversational memory.

## 🚀 Features

* Natural language Q\&A powered by OpenAI's GPT models
* Semantic search using Pinecone vector database
* Contextual understanding via LangChain's retriever + prompt chaining
* Modular design with reusable components

## 🧰 Tech Stack

* [LangChain](https://www.langchain.com/) — for LLM chaining and retrieval logic
* [OpenAI GPT](https://platform.openai.com/docs) — for generating responses
* [Pinecone](https://www.pinecone.io/) — for storing and retrieving document embeddings
* Python 3.8+

---

## 📦 Installation

1. **Clone the repository**

```bash
git clone https://github.com/waizin28/AIChatBot.git
cd AIChatBot
```

2. **Install dependencies from virtual environment**

```bash
source env/bin/activate   # On Windows: env\Scripts\activate
pip install -r requirements.txt
```

3. **Set environment variables**

Create a `.env` file:

```env
OPENAI_API_KEY=your-openai-api-key
PINECONE_API_KEY=your-pinecone-api-key
PINECONE_ENV=your-pinecone-environment
```

---

## 🧠 How It Works

1. **Ingest documents** — your text/csv/pdf files are split into chunks and embedded using OpenAI embeddings.
2. **Store embeddings** — chunks are pushed to Pinecone vector DB for similarity-based search.
3. **Ask questions** — user inputs are processed, top `k` relevant chunks are retrieved.
4. **Generate answer** — the context and question are passed into GPT to produce a coherent response.

---

## 📄 Example Usage

```python
from chatbot import ask_and_get_answer, ingest_documents

# Step 1: Ingest your docs
vector_store = ingest_documents("docs/")

# Step 2: Ask a question
response = ask_and_get_answer(vector_store, "What is the refund policy?")
print(response)
```

---

## 🧪 Development

* `chatbot.py` — core logic for ingestion and Q\&A
* `requirements.txt` — project dependencies
* `example_notebook.ipynb` — interactive notebook demo

---

## ✅ To-Do

* Add support for PDF parsing
* Build web UI with Streamlit or Flask
* Add source document tracking

---

## 🛡️ License

MIT License

---

Let me know if you want this tailored for a specific framework (e.g., Flask/Streamlit UI) or hosted version.
