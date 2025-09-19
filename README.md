# 🧬 Sentence Classification in Biomedical Literature  
*A Study on the PubMed 200k RCT Dataset*  

## 📌 Overview  
Biomedical literature is expanding rapidly, making it difficult for researchers to manually extract relevant information. This project focuses on **automated sentence classification** of biomedical research abstracts using the **PubMed 200k RCT dataset**.  

The dataset is annotated into five categories: **Background, Objective, Methods, Results, and Conclusions**. We compare **traditional machine learning models**, **embedding-based approaches**, and **deep learning models** to evaluate their performance on this task.  

## 📊 Dataset  
- **Total sentences**: 2,270,286  
- **Vocabulary size**: 479,444 unique words  
- **Labels**:  
  - `BACKGROUND` – 196,689 sentences  
  - `OBJECTIVE` – 186,601 sentences  
  - `METHODS` – 722,586 sentences  
  - `RESULTS` – 766,271 sentences  
  - `CONCLUSIONS` – 339,714 sentences  

**Data splits**:  
- Training: 2,211,861  
- Validation: 28,932  
- Test: 29,493  

## ⚙️ Methodology  
### 🔹 Baseline Models (Bag-of-Words + TF-IDF)  
- **Multinomial Naive Bayes**  
- **Logistic Regression**  
- **Random Forest**  

### 🔹 Embedding-Based Models  
- Pre-trained **BioWordVec embeddings**  
- Models: Logistic Regression, LinearSVC  

### 🔹 Deep Learning  
- **Convolutional Neural Network (CNN)** trained on raw text sequences  

### 🔹 Tools & Frameworks  
- **scikit-learn** (Naive Bayes, Logistic Regression, Random Forest, SVM)  
- **gensim** (BioWordVec embeddings)  
- **TensorFlow / Keras** (CNN)  
- **numpy, spacy** (data preprocessing)  
- **matplotlib, seaborn** (visualization)  

## 📈 Results  
| Model | Accuracy (20k Test) | Accuracy (200k Test) |
|-------|---------------------|-----------------------|
| MultinomialNB (CountVectorizer) | 77% | 78.4% |
| Logistic Regression (CountVectorizer) | 80% | 82.7% |
| Random Forest (CountVectorizer) | 78.3% | 58.3% |
| MultinomialNB (TF-IDF) | 74.5% | 77% |
| Logistic Regression (TF-IDF) | 80% | 82.3% |
| Random Forest (TF-IDF) | 78% | 58.9% |
| Logistic Regression (BioWordVec) | 77% | 78.7% |
| LinearSVC (BioWordVec) | 76.6% | 78.1% |
| CNN | **88.5%** | Not run (RAM limitations) |

### 🔑 Key Insights  
- Logistic Regression consistently outperformed Naive Bayes.  
- Random Forests were computationally expensive and performed poorly on 200k.  
- Pre-trained embeddings improved generalization.  
- CNN achieved the **best accuracy (88.5%)**, showing the strength of deep learning.  

Author: 
Maxime Hayakawa Ivanovic
