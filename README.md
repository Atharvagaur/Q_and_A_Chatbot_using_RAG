# 🧠 Conversational Q&A Chatbot using RAG

## 📌 Overview

This project implements a **Conversational Question-Answering Chatbot** using **Retrieval-Augmented Generation (RAG)**.
It combines a **vector database (Chroma)** with a **Large Language Model (LLM)** to generate accurate, context-aware answers from documents.

The system supports **multi-turn conversations** by incorporating chat history and rewriting follow-up queries into standalone questions for better retrieval.

---

## 🚀 Features

* 🔍 **Semantic Search using Chroma Vector Database**
* 💬 **Session-based Conversational Memory**
* 🧠 **History-Aware Query Reformulation**
* 📄 **Document-grounded Answer Generation**
* ⚡ **Efficient Text Chunking & Embedding Pipeline**

---

## 🏗️ Architecture

```
User Query
   ↓
History-Aware Retriever (LLM rewrites query using chat history)
   ↓
Vector Database (Chroma retrieves relevant chunks)
   ↓
Context + Query → LLM
   ↓
Generated Answer
```

---

## 🧩 Tech Stack

* **Language:** Python
* **Framework:** LangChain
* **LLM:** openai/gpt-oss-120b (via Groq)
* **Embeddings:** all-MiniLM-L6-v2 (Hugging Face)
* **Vector Store:** ChromaDB
* **Environment:** Jupyter Notebook

---

## ⚙️ How It Works

1. **Document Processing**

   * Input documents are split into smaller chunks
   * Each chunk is converted into embeddings using *all-MiniLM-L6-v2*

2. **Storage**

   * Embeddings are stored in Chroma vector database

3. **Query Processing**

   * User query is optionally reformulated using chat history
   * Makes follow-up questions context-aware

4. **Retrieval**

   * Retriever fetches top relevant document chunks

5. **Response Generation**

   * Retrieved context + query is passed to the LLM (*gpt-oss-120b via Groq*)
   * Model generates a concise answer

6. **Memory Handling**

   * Chat history is maintained per session
   * Enables coherent multi-turn conversations

---

## ▶️ Usage

1. Clone the repository:

```bash
git clone https://github.com/your-username/rag-chatbot.git
cd rag-chatbot
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Add API key in `.env`:

```
GROQ_API_KEY=your_api_key_here
```

4. Run the notebook:

```bash
jupyter notebook
```

5. Execute the cells and interact with the chatbot
