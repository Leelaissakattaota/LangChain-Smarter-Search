# 🚀 Build a Smarter Search with LangChain Context Retrieval

[![LangChain](https://img.shields.io/badge/Powered%20by-LangChain-green)](https://www.langchain.com/)
[![IBM Watsonx](https://img.shields.io/badge/AI-IBM%20Watsonx.ai-blue)](https://www.ibm.com/watsonx)
[![ChromaDB](https://img.shields.io/badge/Vector%20DB-ChromaDB-orange)](https://www.trychroma.com/)

An advanced **Information Retrieval** system that leverages **Retrieval-Augmented Generation (RAG)** to provide precise, context-aware answers from large document collections.

---

## 📖 Overview
Traditional keyword searches often fail to understand the nuance of human language. This project implements four cutting-edge retrieval strategies to ensure that AI models receive the most relevant information possible.

### 🧠 Key Retrievers Implemented
| Retriever Type | How it Works | Best For... |
| :--- | :--- | :--- |
| **Vector Store-Backed** | Fetches documents using semantic similarity in a high-dimensional space. | Simple, fast semantic search. |
| **Multi-Query** | Uses an LLM to rewrite a single user query into multiple variations to capture different perspectives. | Queries that are vague or complex. |
| **Self-Querying** | Automatically extracts metadata filters (like year or rating) from natural language. | Structured data with tags. |
| **Parent Document** | Finds small relevant chunks but returns the larger "parent" context for the LLM. | Retaining broad context. |

---

## 🛠️ Technology Stack
* **Framework:** `LangChain`
* **LLM:** `IBM watsonx.ai` (Mistral-Small-3-24B-Instruct)
* **Embedding Model:** `ibm/slate-125m-english-rtrvr-v2`
* **Vector Database:** `ChromaDB`
* **File Support:** `.txt` (TextLoader) and `.pdf` (PyPDFLoader)

[Image of LangChain RAG retrieval architecture]

---

## 🏗️ Architecture & Flow
1.  **Ingestion:** Documents are loaded and split into manageable chunks using a `RecursiveCharacterTextSplitter`.
2.  **Embedding:** Text is converted into numerical vectors that represent semantic meaning.
3.  **Indexing:** Vectors are stored in **ChromaDB** for lightning-fast retrieval.
4.  **Retrieval:** Depending on the query, one of the four retrievers fetches the best data points.
5.  **
