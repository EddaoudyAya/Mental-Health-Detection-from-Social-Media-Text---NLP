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
Mental-Health-Detection-from-Social-Media-Text---NLP/
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
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/EddaoudyAya/Mental-Health-Detection-from-Social-Media-Text---NLP.git
cd Mental-Health-Detection-from-Social-Media-Text---NLP
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment.

For Windows:

```bash
venv\Scripts\activate
```

For Linux or macOS:

```bash
source venv/bin/activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## Data

The dataset files are not included in this repository because of size and ethical considerations.

To reproduce the project, the preprocessed data should be placed inside the `data/` folder.

The data preparation steps are available in the notebooks inside the `notebooks/` folder.

---

## Training

Each model can be trained using its corresponding notebook:

- `tf_idf_linear_svm_calibrated.ipynb`
- `bert_model.ipynb`
- `roberta_model.ipynb`

The trained models are saved locally in the `models/` folder.

The `models/` folder is not uploaded to GitHub because trained Transformer models are usually large.

---

## Running the Application

After training the models, run the Streamlit application:

```bash
streamlit run app/streamlit_compare.py
```

The application allows users to:

- Enter a text sample
- Compare predictions from different models
- Display prediction probabilities
- Observe how each model classifies the same input

---

## Evaluation Metrics

The project uses three main evaluation metrics:

- **Accuracy:** measures the overall percentage of correct predictions.
- **Macro F1-score:** calculates the average F1-score across all classes equally.
- **Weighted F1-score:** calculates the F1-score while considering the number of samples in each class.

Macro F1-score is especially important in this project because the dataset is imbalanced.

---

## Ethical Considerations

This project deals with sensitive mental health-related text. Therefore, the following limitations must be considered:

- The system is not a medical diagnosis tool.
- The predictions should not be used for medical decisions.
- The results are only intended for academic analysis and experimentation.
- The dataset may contain bias because it comes from social media text.
- Any real-world use would require medical expertise, ethical validation, and stronger privacy safeguards.


