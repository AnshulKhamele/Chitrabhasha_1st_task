# Topic Classification using Classical and Deep Learning Approaches

---

## 📌 Overview

This project builds an efficient and scalable topic classification system for a large-scale dataset (~10 million samples, ~4GB).

The solution includes:

* Classical Machine Learning models (Naive Bayes, Logistic Regression, SVM)
* Feature engineering (Hashing Vectorizer, TF-IDF)
* Custom CNN model built from scratch (no pretrained models)

---

## ⚙️ Setup Instructions

### 1. Environment Setup

```bash
python -m venv venv
```

Activate:

**Windows:**

```bash
venv\Scripts\activate
```

**Linux/Mac:**

```bash
source venv/bin/activate
```

---

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🏋️ Training Instructions

Run:

```bash
python src/train.py
```

This will:

* Load dataset (subset for efficiency)
* Perform preprocessing
* Train:

  * Naive Bayes
  * Logistic Regression
  * SVM
* Save models in `final_models/`

---

### CNN Training

CNN is trained separately using PyTorch.

Steps:

* Tokenization & vocabulary creation
* DataLoader preparation
* Train for 2 epochs

Model saved as:

```
final_models/cnn_model.pth
```

---

## 🔍 Inference Instructions

Run:

```bash
python src/inference.py
```

Example:

```python
sample = "Latest technology trends in AI"
print(predict(sample))
```

---

## 🔄 Input / Output Schema

### Input

```
"Breaking news in global politics"
```

### Output

```
"Politics"
```

---

## 📊 Models Implemented

| Model               | Feature Type |
| ------------------- | ------------ |
| Naive Bayes         | Hashing      |
| Logistic Regression | Hashing      |
| SVM                 | Hashing      |
| Logistic Regression | TF-IDF       |
| CNN                 | Embedding    |

---

## 🧪 Experiments Summary

### Naive Bayes

* Accuracy: 0.7999
* F1: 0.7902

### Logistic Regression (Hashing)

* Accuracy: 0.8020
* F1: 0.7923

### SVM

* Accuracy: 0.8754
* F1: 0.8707

### TF-IDF + Logistic Regression

* Accuracy: 0.8634
* F1: 0.8556

### CNN (Final Model)

* Accuracy: 0.8770
* F1: 0.8729

---

## 🧠 Key Observations

* SVM significantly outperforms basic linear models
* TF-IDF improves feature quality but is memory intensive
* CNN performs best due to contextual understanding

---

## 📁 Project Structure

```
project/
│── src/
│   ├── train.py
│   ├── inference.py
│   ├── model.py
│   └── utils.py
│── experiments/
│── final_models/
│── report.pdf
│── requirements.txt
│── README.md
```

---

## 🔁 Reproducibility

* Random seeds fixed
* Models and encoders saved
* Pipeline runs end-to-end

---

## 🚀 Highlights

* Handles large dataset efficiently
* Uses memory-optimized HashingVectorizer
* Custom CNN (no pretrained models)
* Strong performance across models

---

## 📌 Notes

* TF-IDF used only on subset due to memory limits
* Hashing ensures scalability
* CNN achieves best performance

---

## ✅ Final Checklist

* [ ] `final_models/` contains saved models
* [ ] `report.pdf` included
* [ ] Code runs using `train.py`
* [ ] README present

---
