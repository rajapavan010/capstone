# PEMSTOE: Permutation Effects in Multilingual Summarization using Transformers via Ordered Evaluation

## 📌 Overview
**PEMSTOE** investigates the impact of **input sentence permutation** on multilingual text summarization using **transformer-based models**.  
The study focuses on summarizing articles in **seven major Indian languages** — Telugu, Urdu, Marathi, Hindi, Tamil, Bengali, and English — by leveraging both **abstractive** and **hybrid extractive–abstractive** approaches.

We fine-tune **mT5** and **IndicBART** models, alongside proposed **hybrid architectures**, and evaluate them using **ROUGE** and **BLEU** metrics under an **ordered evaluation** framework.

---

## 🎯 Objectives
- Analyze the effect of **shuffled training data** with **ordered test evaluation**.
- Compare **pure abstractive** vs. **hybrid extractive–abstractive** summarization methods.
- Identify the most effective model for **multilingual Indian language summarization**.

---

## 🛠 Features
- **Multilingual coverage** (7 Indian languages + English)
- **Hybrid model**: **BERT-based TextRank** + **Transformer-based abstractive models**
- **Permutation-based training** using **Jigsaw Learning**
- **Evaluation** with ROUGE & BLEU scores

---

## 📂 Dataset
- **Source**: [XL-Sum Dataset](https://huggingface.co/datasets/csebuetnlp/xlsum) (BBC news articles in 45 languages)
- **Languages**: Telugu, Urdu, Marathi, Hindi, Tamil, Bengali, English  
- **Samples**: 2000 per language  
- **Processing**: Tokenization, padding, attention masking, label adjustment

---

## 📊 Models Implemented
1. **mT5** — Multilingual Text-to-Text Transformer
2. **IndicBART** — Indic language-specific multilingual BART
3. **Hybrid mT5** — BERT-based TextRank + mT5
4. **Hybrid IndicBART** — BERT-based TextRank + IndicBART

---

## 📈 Results Summary

### ROUGE Scores
| Model           | ROUGE-1 | ROUGE-2 | ROUGE-L | ROUGE-Lsum |
|-----------------|---------|---------|---------|------------|
| mT5             | 0.049   | 0.013   | 0.048   | 0.048      |
| Hybrid mT5      | 0.472   | 0.045   | 0.046   | 0.048      |
| IndicBART       | 0.885   | 0.764   | 0.885   | 0.885      |
| Hybrid IndicBART| **0.895** | **0.775** | 0.881   | 0.870      |

### BLEU Scores
| Model           | BLEU    |
|-----------------|---------|
| mT5             | 0.073   |
| Hybrid mT5      | 0.115   |
| IndicBART       | 0.231   |
| Hybrid IndicBART| **0.275** |

**Key Insight:**  
Hybrid IndicBART outperformed all models in BLEU and achieved competitive ROUGE scores, showing **robustness to input order changes**.

---

## ⚙️ Tech Stack
- **Language**: Python  
- **Libraries**:
  - Hugging Face Transformers
  - PyTorch
  - Scikit-learn
  - Pandas, NumPy
  - NetworkX
  - TQDM
  - Hugging Face Datasets & Evaluate

---

## 📜 How It Works
1. **Data Preparation**: Import multilingual dataset → Preprocess → Tokenize → Pad & mask → Adjust labels
2. **Training**:
   - Shuffle training set (Jigsaw Learning)
   - Keep test set ordered for evaluation
   - Fine-tune mT5, IndicBART, and hybrids
3. **Evaluation**: Measure ROUGE & BLEU scores

---

## 📌 Future Work
- Add **more low-resource Indian languages**
- Explore **cross-lingual summarization**
- Implement **real-time summarization API**
- Test **multimodal summarization** (text + audio/video)

---

## 👨‍💻 Authors
- Pradeep Sai Teja Sanka  
- Raja Pavan Vignesh Kajjayam  
- Sai Karthik Nallamothu  
- Yeswanthvenkatakumar Vidavaluru  

**Supervisor:** Dr. Tapas Kumar Mishra  
**Institution:** SRM University-AP, Andhra Pradesh  

---

## 📄 License
This project is for **academic and research purposes** only.
