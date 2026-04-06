# 🏷️ NLP Token Classification: POS Tagging & Chunking

Fine-tuned DistilBERT models for Part-of-Speech (POS) Tagging and Chunking tasks using the CoNLL-2003 dataset.

---

## 📌 Project Overview

This project implements **token-level classification** using transformer models (DistilBERT) to perform:
1. **POS Tagging** - Grammar-level token classification (47 tags)
2. **Chunking** - Phrase-level grouping (23 chunk tags)

---

## 🎯 Objectives

- Fine-tune pre-trained transformer models for sequence labeling
- Handle subword tokenization and label alignment
- Evaluate models using sequence-based metrics (seqeval)
- Compare POS tagging vs chunking performance

---

## 📊 Dataset

**CoNLL-2003 Dataset** ([eriktks/conll2003](https://huggingface.co/datasets/eriktks/conll2003))
- **Train:** 14,041 samples
- **Validation:** 3,250 samples
- **Test:** 3,453 samples

### Label Types:
- **POS Tags:** 47 grammatical categories (NNP, VBZ, JJ, etc.)
- **Chunk Tags:** 23 IOB-formatted phrase tags (B-NP, I-VP, etc.)

---

## 🛠️ Technical Stack

| Component | Technology |
|-----------|------------|
| **Framework** | Hugging Face Transformers |
| **Model** | DistilBERT (distilbert-base-uncased) |
| **Training** | PyTorch + Trainer API |
| **Evaluation** | seqeval |
| **Platform** | Google Colab (Tesla T4 GPU) |

---

## 📈 Results

### Model Performance

| Task | Precision | Recall | F1 Score |
| :--- | :---: | :---: | :---: |
| **POS Tagging** | 0.9117 | 0.9080 | 0.9098 |
| **Chunking** | 0.9055 | 0.8972 | 0.9013 |

---

### ⚙️ Training Details

| Parameter | Configuration |
| :--- | :--- |
| **Model** | DistilBERT (66.4M parameters) |
| **Epochs** | 3 |
| **Batch Size** | 16 |
| **Learning Rate** | 2e-5 |
| **Training Time** | ~326 seconds (~5.4 minutes) |
| **GPU** | NVIDIA Tesla T4 |

---

### 🧪 Sample Predictions

**Input Sentence:** `"John works at Google in California"`

| Token | POS Tag (Description) | Chunking Tag (BIO) |
| :--- | :--- | :--- |
| **John** | NNP (Proper Noun) | B-NP (Begin Noun Phrase) |
| **works** | VBZ (Verb, 3rd person) | B-VP (Begin Verb Phrase) |
| **at** | IN (Preposition) | B-PP (Begin Prep. Phrase) |
| **Google** | NNP (Proper Noun) | B-NP (Begin Noun Phrase) |
| **in** | IN (Preposition) | B-PP (Begin Prep. Phrase) |
| **California** | NNP (Proper Noun) | B-NP (Begin Noun Phrase) |

---
