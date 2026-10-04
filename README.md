# Mental Health Detection from Social Media Text using NLP

## Overview

This project focuses on the automatic classification of mental health-related states from social media text using Natural Language Processing (NLP) techniques.

The objective is to compare traditional machine learning methods with Transformer-based models in order to evaluate their ability to understand and classify complex textual expressions related to mental health.

The project was developed as an academic work within the Big Data and Artificial Intelligence Engineering program at ENSA Tetouan, during the 2025-2026 academic year.

> **Important note:** This project is for academic and experimental purposes only. It is not a medical diagnosis system and should not be used as a substitute for professional medical advice.

---

## Project Motivation

Social media platforms contain a large amount of user-generated text where people may express emotions, stress, anxiety, depression, or other mental health-related experiences.

This project explores how NLP models can analyze this type of text and classify it into predefined mental health-related categories. The goal is not to diagnose users, but to study how machine learning and deep learning models behave on sensitive and imbalanced text classification problems.

---

## Objectives

The main objectives of this project are:

- Collect and prepare social media text data for NLP classification.
- Formulate the task as a multi-class classification problem.
- Train and compare different NLP models.
- Evaluate the models using metrics adapted to imbalanced datasets.
- Analyze the strengths and limitations of each approach.
- Build a simple interactive application to compare model predictions.

---

## Classes Covered

The classification problem includes 14 categories:

- Depression
- Suicidal
- ADHD
- Bipolar disorder
- Normal
- OCD
- PTSD
- Anxiety
- Stress
- Personality disorder
- Asperger's
- Schizophrenia
- Addiction
- Alcoholism

---

## Methodology

The project follows a complete NLP workflow:

1. **Data collection**  
   Text data was collected from publicly available social media datasets, mainly related to Reddit posts.

2. **Data preprocessing**  
   The text was cleaned, prepared, and structured for machine learning and deep learning models.

3. **Model training**  
   Three approaches were implemented and compared:
   - TF-IDF with Linear SVM
   - BERT
   - RoBERTa

4. **Model evaluation**  
   The models were evaluated using global and class-level metrics.

5. **Application deployment**  
   A Streamlit application was developed to test and compare predictions interactively.

---

## Models Used

### 1. TF-IDF + Linear SVM

This model was used as a baseline.

It relies on TF-IDF vectorization to transform text into numerical features, followed by a Linear SVM classifier.

Main characteristics:

- Classical machine learning approach
- Fast and interpretable
- Uses unigrams and bigrams
- Applies class weighting
- Includes probability calibration

### 2. BERT

BERT was fine-tuned for multi-class text classification.

Main characteristics:

- Transformer-based language model
- Context-aware text representation
- Fine-tuned on the project dataset
- Handles complex language patterns better than classical methods

### 3. RoBERTa

RoBERTa was also fine-tuned and compared with BERT.

Main characteristics:

- Optimized Transformer architecture
- Dynamic masking during pretraining
- Strong performance on NLP classification tasks
- Competitive results compared to BERT

---

## Experimental Results

The models were evaluated using:

- Accuracy
- Macro F1-score
- Weighted F1-score

| Model | Accuracy | Macro F1-score | Weighted F1-score |
|---|---:|---:|---:|
| TF-IDF + Linear SVM | 0.7647 | 0.7889 | 0.7650 |
| BERT | 0.8176 | 0.8429 | 0.8185 |
| RoBERTa | 0.8100 | 0.8400 | 0.8100 |

---

## Results Discussion

The experimental results show that Transformer-based models achieved better performance than the traditional TF-IDF + Linear SVM baseline.

BERT obtained the best overall results, especially in terms of Macro F1-score. This is important because Macro F1-score gives equal importance to all classes, which is useful when working with imbalanced data.

RoBERTa also achieved strong and stable results, very close to BERT.

The baseline model remains useful because it is faster, simpler, and more interpretable, but it is less effective in capturing complex contextual meanings compared to Transformer-based models.

---

## Project Structure

```text
mental-health-detection-nlp/
│
├── app/
│   └── streamlit_compare.py
│
├── notebooks/
│   ├── dataextraction_from_hugging_face.ipynb
│   ├── preprocessing.ipynb
│   ├── preprocessing_final.ipynb
│   ├── tf_idf_linear_svm_calibrated.ipynb
│   ├── bert_model.ipynb
│   └── roberta_model.ipynb
│
├── data/
│   └── .gitkeep
│
├── models/
│   └── .gitkeep
│
├── requirements.txt
└── README.md
