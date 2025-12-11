# 🧠 RAG AI Agent — Automated Policy & FAQ Assistant (n8n + Pinecone + Gemini)

This project is an end-to-end **Retrieval-Augmented Generation (RAG) AI Agent** built using **n8n**, **Pinecone**, **Google Drive**, **HuggingFace embeddings**, and **Gemini Flash via OpenRouter**.  

The system automatically ingests documents, embeds them, stores them in a vector database, and uses an AI agent to answer user questions in real-time through a chat interface.

---
## RAG WorkFlow
![RAG Agent Workflow](./Rag%20agent%20workflow.jpg)
## Chat Interface
![Chat Interface](./Chat%20Interface.jpg)

## 🚀 Features

### **1. Automatic Document Ingestion (Google Drive Trigger)**
- Watches a specific Google Drive folder.
- Whenever a file is uploaded, the workflow downloads it automatically.

### **2. Intelligent Text Processing**
- Uses **Recursive Character Text Splitter** to break large files into chunks.
- Processes the document as binary using n8n’s Default Data Loader.

### **3. Embedding Generation**
- Embeddings generated using **HuggingFace sentence-transformers/all-MiniLM-L6-v2**.
- Each chunk is vectorized and prepared for storage.

### **4. Vector Database (Pinecone)**
- The processed chunks are stored in a Pinecone index (`policy`) under namespace `Policyy`.
- A second Pinecone instance is connected as a retrieval tool for the Agent.

### **5. RAG-Based AI Agent**
- Uses **Gemini 2.0 Flash via OpenRouter** as the LLM.
- Retrieval is handled through the Pinecone_Vector_Store tool.
- Agent receives a system prompt instructing it to ALWAYS search the vector store before answering.
- Chat interface powered by n8n Chat Trigger.

### **6. Conversational Memory**
- Simple buffer memory retains the last 10 interactions to keep responses coherent.

---

## 🧩 Architecture Overview

 Google Drive → Download File → Text Loader → Text Splitter → Embeddings → Pinecone Storage
↓
Chat Trigger → AI Agent (Gemini) → Pinecone Retrieval → Final Answer

## 🎯 Purpose & Use Cases

- Automated Company Policy Chatbot  
- Internal Knowledge Base Search Agent  
- Smart FAQ Assistant  
- Document Intake + Retrieval System 

## 🙌 Author

**Daniyal Haider**  
AI Engineer & Data Science Enthusiast  
LinkedIn: https://www.linkedin.com/in/daniyal-haider83/  
GitHub: https://github.com/Daniyal-DS

