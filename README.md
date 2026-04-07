# RAG Chatbot using Flowise

A Retrieval-Augmented Generation (RAG) chatbot built with **Flowise** that enables users to ask questions from uploaded documents and receive intelligent, context-aware responses. This project uses **Google Gemini Embeddings**, **Mistral AI**, **In-Memory Vector Store**, and **Conversational Retrieval QA Chain** for efficient document-based question answering.

---

## 🚀 Features

- 📄 Upload and process PDF/documents
- ✂️ Recursive text chunking for better retrieval
- 🧠 Semantic search using Google Gemini Embeddings
- 📦 In-Memory Vector Store for fast retrieval
- 🤖 Response generation using Mistral AI
- 💬 Conversational Retrieval QA Chain for contextual chat
- 📝 Buffer Memory to maintain conversation history
- 🔍 Accurate document-based answers using RAG architecture

---

## 🛠️ Tech Stack

- **Flowise**
- **Google Gemini Embeddings**
- **Mistral AI**
- **Recursive Character Text Splitter**
- **File Loader**
- **In-Memory Vector Store**
- **Buffer Memory**
- **Conversational Retrieval QA Chain**

---

## 📌 Workflow Architecture

The chatbot flow is built in Flowise with the following pipeline:

1. **Recursive Character Text Splitter**
   - Chunk Size: `1000`
   - Chunk Overlap: `200`

2. **File Loader**
   - Loads the input document (PDF or text file)

3. **Google Gemini Embedding**
   - Model: `gemini-embedding-001`
   - Task Type: `RETRIEVAL_DOCUMENT`

4. **In-Memory Vector Store**
   - Stores embedded document chunks
   - Top K Retrieval: `4`

5. **Mistral AI**
   - Model: `mistral-tiny`
   - Temperature: `0.9`

6. **Buffer Memory**
   - Maintains conversational context

7. **Conversational Retrieval QA Chain**
   - Combines retriever + LLM + memory
   - Generates accurate, context-aware answers from the document
   - <img width="1830" height="898" alt="Screenshot 2026-04-07 121804" src="https://github.com/user-attachments/assets/f8ccbccc-02dd-4ecb-ad10-96194d64e021" />


---

## 🧩 Flowise Node Configuration

### 1. Recursive Character Text Splitter
- **Chunk Size:** 1000
- **Chunk Overlap:** 200

### 2. File Loader
- Used to upload and load source documents

### 3. Google Gemini Embedding
- **Provider:** Google Generative AI
- **Model:** `gemini-embedding-001`
- **Task Type:** `RETRIEVAL_DOCUMENT`

### 4. In-Memory Vector Store
- **Top K:** 4

### 5. Mistral AI
- **Model:** `mistral-tiny`
- **Temperature:** 0.9

### 6. Buffer Memory
- Stores conversation history for contextual continuity

### 7. Conversational Retrieval QA Chain
- Connects:
  - Chat Model
  - Vector Store Retriever
  - Memory

---

## 📂 Project Structure

```bash
RAG-Chatbot/
│── README.md
│── RAG_CHATBOT_Chatflow.json
│── sample-document.pdf
