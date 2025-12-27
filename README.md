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

## Finite State Machine
<img src="FSM.png" width="60%">

## WorkFlow
<img src="workflow.png" width="60%">

## Usage

https://colab.research.google.com/drive/13dNnj0nxg3BTzj04QrNRL0kCHn-zb-rQ?usp=sharing

### 1. Open Colab and Add Your API key
<img src="secret.png" width="30%">

### 2. Download Data and Upload (Cell 1)

<img src="file.png" width="30%">

### 3. Download Module (Cell 2, 3)
Return Error Messeage is true, because we restarted kernel here.

<img src="Error_msg.png" width="30%">

### 4. Create FAISS Data (Cell 4, 5)

### 5. Open Gradio UI and Start! (Cell 6)

<img src="result.png" width="60%">
