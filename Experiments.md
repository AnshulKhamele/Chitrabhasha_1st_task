# Experiments Log – Topic Classification

## Overview
This document records the experimentation process followed during model development, including different approaches, observations, and improvements.

---

## Experiment 1: Naive Bayes (Hashing Features)

**Reason:**
- Simple baseline
- Fast training

**Setup:**
- HashingVectorizer (2^18 features)
- MultinomialNB

**Result:**
- Accuracy: 0.7999
- F1 Score: 0.7902

**Observation:**
- Performs reasonably well
- Struggles with complex relationships

---

## Experiment 2: Logistic Regression (SGD)

**Reason:**
- Strong linear baseline
- Works well with sparse features

**Setup:**
- HashingVectorizer
- SGDClassifier (log_loss)

**Result:**
- Accuracy: 0.8020
- F1 Score: 0.7923

**Observation:**
- Slight improvement over Naive Bayes
- More stable predictions

---

## Experiment 3: SVM (SGD Hinge Loss)

**Reason:**
- Effective for high-dimensional sparse data

**Setup:**
- HashingVectorizer
- SGDClassifier (hinge loss)

**Result:**
- Accuracy: 0.8754
- F1 Score: 0.8707

**Observation:**
- Significant performance improvement
- Good generalization

---

## Experiment 4: TF-IDF + Logistic Regression

**Reason:**
- Standard NLP baseline

**Setup:**
- TF-IDF (10K features)
- SGDClassifier

**Result:**
- Accuracy: 0.8634
- F1 Score: 0.8556

**Challenges:**
- High memory usage
- Slow computation on large data

**Observation:**
- Good performance but not scalable

---

## Experiment 5: CNN (Deep Learning)

**Reason:**
- Capture contextual patterns
- Improve performance over linear models

**Setup:**
- Embedding layer (128 dim)
- Conv1D layers (3,4,5 kernels)
- Dropout + Fully Connected

**Result:**
- Accuracy: 0.8770
- F1 Score: 0.8729

**Observation:**
- Best performance among all models
- Captures semantic relationships better

---

## Final Decision

The CNN model was selected as the final model because:
- Highest accuracy and F1 score
- Better handling of contextual information

Classical models were retained for:
- Baseline comparison
- Efficiency analysis

---

## Key Learnings

- HashingVectorizer is highly scalable
- TF-IDF is effective but memory-intensive
- Deep learning models outperform classical models for complex patterns
- Hardware constraints strongly influence design choices