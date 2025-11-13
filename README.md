# AI-ML-Assignment-5-Simple-RAG  
**Author:** Yisakor Mirany 
**Embedding Model:** all-MiniLM-L6-v2  
**LLM:** google/flan-t5-small  
**Vector Store:** FAISS  

---

## 🔍 Summary  
This project implements a simple Retrieval-Augmented Generation (RAG) pipeline using a custom knowledge base derived from a fictional 2024 research paper titled **“Adaptive Retrieval-Augmented Generation for Memory-Constrained Edge Devices.”**

The system:  
- Creates embeddings for KB text  
- Indexes them in FAISS  
- Retrieves top chunks via similarity search  
- Augments a FLAN-T5 LLM to produce grounded answers  

---

## 📚 Test Case Retrieval Summary

### **Test Case 1 — Factual**
**Question:**  
“What is the purpose of the Relevance-Weighted Cache?”

**Retrieved Chunks:**  
Primarily chunk 2 (RWC description).

**Outcome:**  
The system correctly identifies the RWC and its role.

---

### **Test Case 2 — Foil / Not in KB**
**Question:**  
“How does Adaptive RAG compare to ChatGPT-4?”

**Outcome:**  
The system should not find relevant KB information and the generation should avoid hallucinating, showing RAG grounding.

---

### **Test Case 3 — Synthesis**
**Question:**  
“How does Adaptive RAG reduce memory usage while improving retrieval latency?”

**Retrieved Chunks:**  
Combination of chunk 1 and chunk 2 (sliding window + RWC).

**Outcome:**  
The system synthesizes from multiple KB segments.

---

## 🎯 Hallucination Analysis  
When comparing raw LLM responses with RAG-augmented answers, the system demonstrates:  
- More factual accuracy  
- Less hallucination  
- Higher grounding due to retrieved context  

RAG effectively anchors generation to the KB and reduces unsupported claims.

---
