# 🚀 Build a Smarter Search with LangChain Context Retrieval

[![LangChain](https://img.shields.io/badge/Powered%20by-LangChain-green)](https://www.langchain.com/)
[![IBM Watsonx](https://img.shields.io/badge/AI-IBM%20Watsonx.ai-blue)](https://www.ibm.com/watsonx)
[![ChromaDB](https://img.shields.io/badge/Vector%20DB-ChromaDB-orange)](https://www.trychroma.com/)

An advanced **Information Retrieval** system that leverages **Retrieval-Augmented Generation (RAG)** to provide precise, context-aware answers from large document collections.

---

## 📖 Overview
Traditional keyword searches often fail to understand the nuance of human language. [cite_start]This project implements four cutting-edge retrieval strategies to ensure that AI models receive the most relevant information possible[cite: 1, 3].

### 🧠 Key Retrievers Implemented
| Retriever Type | How it Works | Best For... |
| :--- | :--- | :--- |
| **Vector Store-Backed** | [cite_start]Fetches documents using semantic similarity in a high-dimensional space[cite: 4]. | Simple, fast semantic search. |
| **Multi-Query** | [cite_start]Uses an LLM to rewrite a single user query into multiple variations to capture different perspectives[cite: 5, 34]. | Queries that are vague or complex. |
| **Self-Querying** | [cite_start]Automatically extracts metadata filters (like year or rating) from natural language[cite: 17, 35]. | Structured data with tags. |
| **Parent Document** | [cite_start]Finds small relevant chunks but returns the larger "parent" context for the LLM[cite: 27, 36]. | Retaining broad context. |

---

## 🛠️ Technology Stack
* [cite_start]**Framework:** `LangChain` [cite: 1, 3]
* [cite_start]**LLM:** `IBM watsonx.ai` (Mistral-Small-3-24B-Instruct) [cite: 7]
* **Embedding Model:** `ibm/slate-125m-english-rtrvr-v2`
* **Vector Database:** `ChromaDB`
* [cite_start]**File Support:** `.txt` (TextLoader) and `.pdf` (PyPDFLoader) [cite: 9, 21]



---

## 🏗️ Architecture & Flow
1.  [cite_start]**Ingestion:** Documents are loaded and split into manageable chunks using a `RecursiveCharacterTextSplitter`[cite: 4, 28].
2.  **Embedding:** Text is converted into numerical vectors that represent semantic meaning.
3.  **Indexing:** Vectors are stored in **ChromaDB** for lightning-fast retrieval.
4.  **Retrieval:** Depending on the query, one of the four retrievers fetches the best data points.
5.  **Generation:** The retrieved context is passed to the LLM to generate a grounded response.

---

## ⚙️ Installation & Setup
To run this project locally, ensure you have Python installed, then run:

```bash
pip install ibm-watsonx-ai langchain langchain-ibm langchain-community chromadb pypdf lark
