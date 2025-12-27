# VietRAG Travel Agent
## Introduction
VietRAG Travel Agent is a RAG‑powered Vietnam travel assistant that combines fast FAISS vector retrieval, Sentence‑Transformers embeddings, and LLM generation via Ollama to deliver concise, source‑grounded travel advice. It indexes local documents into chunked vectors, uses cosine‑style similarity (IndexFlatIP) to fetch the top‑k most relevant passages, and assembles those passages into a provenance‑aware prompt for the LLM. The system exposes an interactive Gradio UI for real‑time queries and lets users tune retrieval depth with a top‑k slider, enabling tradeoffs between brevity and coverage. Typical use cases include city‑specific guides (Ho Chi Minh, Hanoi), itinerary planning, local dining and transport tips, and FAQ resolution with explicit source citations.

- **FAISS** for vector search
- **Sentence‑Transformers (all‑MiniLM‑L6‑v2)** for embeddings
- **NumPy** for vector math and normalization
- **Ollama API** for generation
- **Gradio** for the web UI
- **JSON + persisted FAISS indices** for data management
- RAG architecture (retrieval + generation) with configurable top‑k retrieval.

## Data
Hanoi.docx and HoChiMinh.docx are the primary external knowledge bases for RAG system. They serve as the authoritative local content that gets chunked, embedded, and indexed into FAISS. These documents provide the factual grounding that the LLM uses to produce source‑backed answers and reduce hallucinations.
