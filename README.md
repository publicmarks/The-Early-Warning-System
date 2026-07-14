# AI-Based Early Warning System for Suicide Ideation Detection Using NLP

> An AI-assisted Natural Language Processing (NLP) framework for detecting suicide ideation in text, designed to support early identification of at-risk military personnel through ethical human-in-the-loop decision making.

## Overview

This project explores the use of Machine Learning and Natural Language Processing (NLP) to detect suicide ideation from written text. The system compares traditional machine learning models with a transformer-based deep learning model to determine the most effective approach for early risk identification.

The project was developed as a capstone project and emphasizes **ethical AI deployment**, ensuring that AI augments—rather than replaces—clinical judgment.

**Important:** This repository is intended for **research and educational purposes only** and **must not** be used as a standalone clinical decision-making system. :contentReference[oaicite:0]{index=0}

---

# Objectives

The project aims to:

- Detect linguistic markers associated with suicide ideation.
- Develop NLP-based machine learning models for binary text classification.
- Compare classical machine learning algorithms with transformer-based models.
- Evaluate performance using standard classification metrics.
- Explore explainable AI and ethical considerations for mental health applications. :contentReference[oaicite:1]{index=1}

---

# Dataset

**Source**

- Suicidal Ideation Reddit Annotated Dataset
- Publicly available on Kaggle
- Binary labeled Reddit posts

**Dataset Statistics**

| Attribute | Value |
|-----------|-------|
| Total Records | 12,656 |
| Usable Records | 12,615 |
| Positive Class | 6,609 |
| Negative Class | 6,047 |

The dataset contains anonymized Reddit posts labeled as either:

- **1** — Suicidal Ideation
- **0** — Non-risk :contentReference[oaicite:2]{index=2}

---

# Project Workflow

```
Raw Reddit Posts
        │
        ▼
Text Cleaning
        │
        ▼
Feature Engineering
        │
        ▼
TF-IDF Vectorization
        │
        ▼
Model Training
(Logistic Regression / SVM / BERT)
        │
        ▼
Evaluation
        │
        ▼
Explainability (LIME)
        │
        ▼
Ethical AI Assessment
```

---

# Preprocessing

The preprocessing pipeline includes:

- Lowercasing
- Punctuation removal
- Tokenization
- Stopword removal
- Lemmatization
- TF-IDF vectorization
- SMOTE oversampling (classical ML models)

Additional domain-derived features:

- Word count
- Character count
- First-person pronoun frequency :contentReference[oaicite:3]{index=3}

---

# Models Evaluated

## 1. Logistic Regression

- TF-IDF features
- SMOTE balancing

---

## 2. Support Vector Machine (SVM)

- RBF kernel
- TF-IDF features
- SMOTE balancing

---

## 3. BERT (bert-base-uncased)

Fine-tuned using:

- 3 epochs
- Learning rate = 5e-5
- Batch size = 16
- Maximum sequence length = 128
- Class weighting instead of SMOTE :contentReference[oaicite:4]{index=4}

---

# Results

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|-------|----------|-----------|--------|------|---------|
| Logistic Regression | 0.8824 | 0.8911 | 0.8730 | 0.8820 | 0.9461 |
| SVM | 0.8756 | 0.8773 | 0.8753 | 0.8763 | 0.9333 |
| **BERT** | **0.8870** | **0.8705** | **0.9206** | **0.8949** | **0.9550** |

### Best Performing Model

**BERT** achieved the highest recall and ROC-AUC, making it the preferred model for suicide ideation detection where minimizing false negatives is critical. :contentReference[oaicite:5]{index=5}

---

# Explainable AI

The project incorporates **LIME (Local Interpretable Model-Agnostic Explanations)** to improve transparency and interpret individual model predictions.

The explainability analysis showed:

- Strong performance on explicit suicidal language
- Reduced sensitivity to indirect or implicit expressions of distress
- Consistent lexical bias across training runs :contentReference[oaicite:6]{index=6}

---

# Ethical Considerations

This project follows a **Human-in-the-Loop AI** framework.

The model is designed to:

- Assist counselors
- Flag potentially high-risk text
- Support clinical triage

The model **does not** replace licensed mental health professionals.

Ethical recommendations include:

- Human review of all flagged cases
- Threshold tuning
- Dataset expansion
- Fairness auditing
- Future demographic validation :contentReference[oaicite:7]{index=7}

---

# Technologies Used

- Python
- Google Colab
- Scikit-learn
- TensorFlow
- Hugging Face Transformers
- Pandas
- NumPy
- Matplotlib
- LIME
- imbalanced-learn (SMOTE)

---

# Repository Structure

```
├── data/
│   └── dataset
│
├── notebooks/
│   └── model_training.ipynb
│
├── models/
│   └── trained_models
│
├── figures/
│   ├── EDA
│   ├── PCA
│   ├── Confusion Matrix
│   └── LIME
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

# Future Improvements

- Fine-tune larger transformer models
- Cross-validation on multiple datasets
- Incorporate multimodal features (speech and physiological signals)
- Improve detection of implicit suicidal language
- Deploy a secure clinician dashboard
- Conduct fairness evaluations using demographic-aware datasets

---

# Disclaimer

This project is intended solely for academic research and educational purposes.

The outputs generated by this model should **never** be interpreted as a clinical diagnosis or used independently for mental health decisions. Any deployment involving real individuals must involve qualified mental health professionals and comply with ethical, institutional, and legal standards.

---

# Citation

If you use this repository in academic work, please cite:

> Publico, M. R. (2026). *AI-Based Early Warning System for Suicide Ideation Detection Using Natural Language Processing: A Human-Centered Framework for Military Mental Health*. Capstone Project.

---

# Author

**Marco R. Publico**

- Registered Guidance Counselor
- Military Officer
- Researcher in AI Applications for Military Mental Health

---

## License

This repository is released for academic and research purposes.

Please provide appropriate attribution when using or adapting this work.
