# 📄 PDF-based Retrieval-Augmented Generation (RAG)

This project implements a **Retrieval-Augmented Generation (RAG)** pipeline for answering questions based on **scanned PDF documents** using OCR, dense embeddings, and a local Large Language Model (LLM).

The system is designed to run efficiently on **Kaggle** and follows best practices for scalable and explainable RAG systems.

---

## 🚀 Features

- OCR for scanned PDF documents using **Tesseract**
- Text cleaning and chunking optimized for OCR output
- Semantic embedding using **BAAI/bge-m3**
- Fast vector search with **FAISS**
- Retrieval-Augmented prompt injection
- Question Answering with **Sahabat AI v1 8B Instruct**
- Persistent FAISS index (no re-embedding needed)

---

## 🧠 RAG Architecture

PDF (Scanned)
↓
OCR (Tesseract)
↓
Text Cleaning
↓
Chunking
↓
Embedding (bge-m3)
↓
FAISS Vector Index
↓
Retriever (Top-K)
↓
Augmented Prompt
↓
LLM (Sahabat AI)
↓
Answer


---

## 🛠️ Tech Stack

| Component | Technology |
|---------|-----------|
| OCR | Tesseract OCR |
| Embedding | BAAI/bge-m3 |
| Vector Database | FAISS |
| LLM | Sahabat AI v1 8B Instruct |
| Frameworks | Sentence-Transformers, HuggingFace Transformers |
| Environment | Kaggle Notebook (GPU P100 recommended) |

---

## 📦 Installation

```bash
pip install sentence-transformers transformers accelerate faiss-cpu pytesseract pillow
apt-get install tesseract-ocr tesseract-ocr-ind

.
├── chunks.pkl
├── data.pdf
├── index.faiss
├── notebook.ipynb
└── README.md

import faiss
index = faiss.read_index("faiss_store/index.faiss")
```
