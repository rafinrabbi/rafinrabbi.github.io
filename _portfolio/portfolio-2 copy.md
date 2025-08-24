---
title: "Bangla QnA Bot (RAG + LangChain)"
excerpt: "Question‑Answering chatbot for Bengali using Retrieval‑Augmented Generation <br/><img src='/images/rsz_screenshot_from_2025-07-26_11-12-30.png'>"
collection: portfolio
---

### Overview
**Bangla QnA Bot** is a Bengali question‑answering system built with **Retrieval‑Augmented Generation (RAG)**. It indexes a document corpus, retrieves the most relevant passages for a query, and then generates **grounded** answers in Bangla via an LLM orchestrated with **LangChain**.

### Key Features
- **End‑to‑end RAG pipeline**: loaders → chunking → embeddings → vector store → retriever → generator.
- **Bengali‑aware preprocessing** for cleaner sentence boundaries and better retrieval.
- **Configurable backends**: swap embedding models and LLMs without changing app logic.
- **Deterministic answering**: includes retrieved contexts to keep responses faithful to source.
- **CLI / API ready**: simple interfaces for local testing or app integration.

### Tech Stack
- **LangChain** for chains, retrievers, and prompt orchestration  
- **Vector store**: FAISS / Chroma (configurable)  
- **Embeddings**: SBERT / Hugging Face models suited to Bangla (configurable)  
- **LLM**: pluggable (OpenAI/Gemini/Local) via LangChain wrappers  
- **Python**, **FastAPI/Streamlit (optional UI)**

### How It Works
1. **Ingest & Chunk**: Documents are loaded and split using Bengali‑aware rules (`।` as a primary separator).  
2. **Embed & Index**: Chunks are embedded and stored in a vector database.  
3. **Retrieve**: For a user query, the retriever pulls top‑k semantically similar chunks.  
4. **Generate**: The LLM receives the query + retrieved context and returns a **Bangla** answer.  
5. **(Optional) Cite**: Return source snippets for transparency.