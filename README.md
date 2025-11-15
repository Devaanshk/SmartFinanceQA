# SmartFinanceQA

SmartFinanceQA is a **domain-specific, Retrieval-Augmented Generation (RAG)** system designed to answer retail-investor financial questions with **high accuracy, minimal hallucination, and strong grounding** in authoritative sources (e.g., Investopedia).

The system combines **hybrid retrieval** (BM25 + dense embeddings), a **fine-tuned LLM**, and a clean evaluation pipeline to consistently outperform baseline LLM responses.

---

## 🔍 Overview

Retail investors often ask open-ended questions requiring concise, trustworthy explanations:

> “What is diluted EPS?”  
> “How does duration affect bond prices?”  
> “What happens during a reverse stock split?”

Most LLMs hallucinate or give incomplete answers.  
SmartFinanceQA solves this by:

- Retrieving **relevant financial definitions and explanations**
- Feeding them into a **fine-tuned LLM**
- Producing **grounded, accurate answers** backed by real context

---

## 🚀 Key Features

- **Hybrid Retrieval Pipeline**  
  Combines BM25 lexical retrieval with semantic embedding search for improved recall.

- **Fine-Tuned LLM**  
  Customized on thousands of question–answer pairs to produce structured, domain-aware responses.

- **RAG Architecture**  
  Ensures factuality and reduces hallucination by supplying retrieved passages to the LLM.

- **Evaluation Framework**  
  Includes ROUGE-L and F1 scoring to compare model outputs with ground-truth answers.

- **Extensible Codebase**  
  Modular Python scripts (retriever, ingestion, finetuning, evaluation) allow fast iteration.

---

## 🧠 High-Level Architecture


       ┌─────────────────┐
       │  User Question  │
       └────────┬────────┘
                │
    ┌───────────▼────────────┐
    │   Hybrid Retriever      │
    │ (BM25 + Embeddings)     │
    └───────────┬────────────┘
                │ Top-K Passages
       ┌────────▼─────────┐
       │    RAG Prompt    │
       │ (Context + Q)    │
       └────────┬─────────┘
                │
       ┌────────▼────────┐
       │  Fine-Tuned LLM │
       └────────┬────────┘
                │
       ┌────────▼────────┐
       │  Final Answer   │
       └─────────────────┘


---

## 📁 Repository Structure

SmartFinanceQA/
├── ingestion.py # Data loading & preprocessing
├── retriever.py # BM25 + embedding retriever
├── hybrid_retriever.py # Combined hybrid search
├── llm_model.py # LLM wrapper & RAG prompt builder
├── finetuned_llm.py # Fine-tuned LLM interface
├── NLP_Finetuned.py # Training & evaluation script
├── embedding_visualization.py# Embedding analysis utilities
├── requirements.txt # Dependencies
└── README.md


---

## ⚙️ Setup Instructions

```bash
git clone https://github.com/Devaanshk/SmartFinanceQA.git
cd SmartFinanceQA
pip install -r requirements.txt
Set your API keys (if needed):


export OPENAI_API_KEY="your_key_here"
▶️ Running the System
Run the full pipeline:


python main.py
Run ingestion only:


python ingestion.py
Evaluate model quality:


python NLP_Finetuned.py
📊 Results (Summary)
SmartFinanceQA produces:

Higher ROUGE-L scores

More accurate definitions

Reduced hallucination

Cleaner, structured outputs compared to baseline LLM responses

(Exact metrics can be added here if you want them public.)

📝 Project Motivation & Story
This project was built to develop a reliable, finance-specific Q&A system that avoids generic or hallucinated model outputs.
The intent was to design a pipeline used by analysts, students, and retail investors to quickly obtain short, accurate, and context-backed explanations of financial terms and concepts.

SmartFinanceQA demonstrates:

End-to-end RAG development

Retrieval engineering

Model training & fine-tuning

Evaluation & analysis

Production-ready code organization

It appears on my resume under:

“RAG-based Finance Q&A System”

👤 Author
Devaansh Kataria
M.S. in Data Science, Stony Brook University
Focused on LLMs, RAG systems, and applied ML
