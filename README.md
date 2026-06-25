# 🩺 Medical RAG Assistant using TinyLlama and FAISS

## 📌 Overview

Medical RAG Assistant is a Retrieval-Augmented Generation (RAG) chatbot that answers healthcare-related questions using a verified medical knowledge base built from the MedQuAD dataset.

The system first retrieves the most relevant medical document using semantic search with FAISS and Sentence Transformers. If a highly relevant document is found, the chatbot generates a grounded response using TinyLlama. For unseen medical topics, it falls back to TinyLlama's general medical knowledge while clearly informing the user that the answer is not from the verified knowledge base.

---

## ✨ Features

* 🩺 Medical Question Answering
* 🔍 Semantic Search using FAISS
* 🤖 TinyLlama Response Generation
* 📚 MedQuAD Knowledge Base
* 🎯 Confidence-based Retrieval
* 💬 Interactive Gradio Interface
* ❌ Non-medical Query Rejection
* 📊 Model Evaluation

---

## 🛠️ Tech Stack

* Python
* Pandas
* LangChain
* Sentence Transformers (all-MiniLM-L6-v2)
* FAISS
* TinyLlama
* Hugging Face Transformers
* Gradio
* Scikit-learn

---

## 📂 Dataset

**Dataset:** MedQuAD

After preprocessing:

* Training Samples: **13,085**
* Validation Samples: **1,636**
* Test Samples: **1,636**

The dataset was cleaned to remove webpage navigation text, animation instructions, and other non-medical artifacts before indexing.

---

## ⚙️ System Pipeline

User Query

↓

Sentence Transformer Embedding

↓

FAISS Semantic Search

↓

Top-1 Retrieval

↓

Similarity Threshold

↓

Verified MedQuAD Response

OR

TinyLlama General Medical Response

↓

Final Answer

---

## 📈 Evaluation Results

| Metric                   |             Score |
| ------------------------ | ----------------: |
| Top-3 Retrieval Accuracy |        **69.62%** |
| Precision                |        **49.42%** |
| Recall                   |        **50.43%** |
| F1-Score                 |        **48.72%** |
| Average ROUGE-L          |        **0.1597** |
| Average BERTScore (F1)   |        **0.8237** |
| Average Inference Time   | **24.65 s/query** |

*ROUGE-L and BERTScore were computed on a randomly selected subset of 100 samples from the held-out test set due to computational cost.*

---

## 🚀 How to Run

1. Clone the repository.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open **Medical_RAG_Assistant.ipynb**.
4. Run all notebook cells.
5. Launch the Gradio interface and start asking medical questions.

---

## 🔮 Future Improvements

* Integrate BioBERT embeddings
* Add PubMed/MedlinePlus retrieval
* Introduce reranking models
* Deploy on Hugging Face Spaces
* Replace TinyLlama with a larger medical LLM

---

## 👨‍💻 Author

**Priyangsu Kesh**
