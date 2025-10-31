# Local-LLM-Document-Analysis-System-RAG-with-LangChain-FAISS-and-Ollama-
Local RAG system using LangChain, FAISS, and Ollama to read and analyze any document offline. Combines semantic search with local LLMs to extract insights and cite sources from 10-Ks, bills, reports, or research papers.


🧠 Local LLM Document Analysis System (RAG with LangChain, FAISS & Ollama)

This project is a local Retrieval-Augmented Generation (RAG) system that allows you to read, search, and analyze any document — from SEC 10-K filings to government bills, contracts, or research papers — using open-source Large Language Models (LLMs).
It runs entirely offline, combining semantic search and local model reasoning to produce grounded, citation-based answers.

The system automatically loads, cleans, and chunks documents, then converts text into numerical embeddings for similarity search. A local vector store (FAISS) retrieves the most relevant sections, which are then passed to a locally hosted LLM (Llama 3 via Ollama) for contextual summarization and question answering.

Built initially to analyze financial filings such as Apple’s, Tesla’s, and JPMorgan’s 10-K reports, the pipeline is fully general-purpose and can handle any combination of .pdf, .html, .xml, or .txt files.

🔍 Features
	•	Offline Operation – No external API keys or cloud services required.
	•	Multi-Document Search – Drop in multiple files and query them simultaneously.
	•	RAG Architecture – Combines dense vector retrieval (FAISS) with reasoning from local LLMs.
	•	Citation-Based Responses – Every answer references the original document source.
	•	Extendable – Easily add support for new formats or swap embedding/LLM models.

🧩 Tech Stack
	•	Python, LangChain, FAISS, PyTorch
	•	Ollama (Llama 3), Sentence-Transformers (MiniLM-L6-v2)
	•	BeautifulSoup, Jupyter Notebook

⚙️ Typical Workflow
	1.	Place documents into data/raw/.
	2.	Run python -m app.ingest to build the FAISS index.
	3.	Query locally:
    from app.rag import build_chain
    chain = build_chain()
    q = "What supply-chain risks does Tesla mention?"
    print(chain.invoke(q).content)

This project demonstrates how open-source LLMs and local vector search can transform static documents into an interactive, privacy-preserving knowledge assistant.
