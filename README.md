# Question Type Classification using BERT and Linear SVM

An NLP project that classifies natural language questions into predefined categories using both a traditional machine learning model (Linear SVM) and a transformer-based deep learning model (BERT).

---

## Project Overview

Question classification is one of the fundamental Natural Language Processing (NLP) tasks. The objective is to automatically determine the type of question being asked so that intelligent systems such as chatbots, virtual assistants, and search engines can provide accurate answers.

This project compares two different approaches:

- Linear Support Vector Machine (Linear SVM)
- Fine-Tuned BERT (bert-base-uncased)

The performance of both models is evaluated using standard classification metrics.

---

## Dataset

**Dataset:** TREC Question Classification Dataset

The dataset contains thousands of English questions divided into six categories:

- Human
- Entity
- Description
- Numeric
- Location
- Abbreviation

The original training and testing splits were used, while part of the training data was reserved for validation during transformer fine-tuning.

---

## Objectives

The main objectives of this project are:

- Build a baseline machine learning classifier.
- Fine-tune a transformer model for question classification.
- Compare classical NLP with modern transformer architectures.
- Evaluate both models using multiple performance metrics.

---

## Models Implemented

### Linear SVM

Traditional machine learning model using:

- TF-IDF Vectorization
- Unigrams
- Bigrams

### BERT

Transformer Model:

- bert-base-uncased
- Fine-tuned for multiclass classification
- Hugging Face Transformers

---

## Technologies Used

- Python
- Hugging Face Transformers
- Hugging Face Datasets
- PyTorch
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn

---

## Project Pipeline

```
Load Dataset
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Data Cleaning
        │
        ▼
TF-IDF Feature Extraction
        │
        ▼
Train Linear SVM
        │
        ▼
BERT Tokenization
        │
        ▼
Fine-Tune BERT
        │
        ▼
Model Evaluation
        │
        ▼
Performance Comparison
```

---

## BERT Training Configuration

| Parameter | Value |
|------------|------:|
| Model | bert-base-uncased |
| Epochs | 4 |
| Batch Size | Dynamic Padding |
| Learning Rate | 2e-5 |
| Optimizer | AdamW |
| Validation Split | 15% |
| Maximum Sequence Length | 64 Tokens |

---

## Performance Comparison

| Model | Accuracy | Precision | Recall | F1 Score |
|--------|----------|-----------|--------|----------|
| Linear SVM | 88.80% | 89.21% | 88.80% | 88.73% |
| BERT | **97.40%** | **97.91%** | **95.91%** | **96.81%** |

The fine-tuned BERT model achieved significantly higher performance by understanding contextual information instead of relying only on word frequency.

---

## Repository Structure

```
Question-Type-Classification/
│
├── LLm_Abhi.ipynb
├── README.md
├── requirements.txt
├── report.pdf
├── figures/
│   ├── class_distribution.png
│   ├── confusion_matrix.png
│   ├── training_accuracy.png
│   └── validation_loss.png
└── outputs/
    ├── predictions.csv
    └── evaluation_results.csv
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/yourusername/question-type-classification.git
```

Move into the project folder

```bash
cd question-type-classification
```

Install required packages

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```
LLm_Abhi.ipynb
```

---

## Python Libraries

```
transformers
datasets
torch
scikit-learn
numpy
pandas
matplotlib
seaborn
evaluate
accelerate
```

---

## Sample Predictions

| Question | Predicted Category |
|-----------|-------------------|
| Who invented the telephone? | Human |
| What is the capital of Japan? | Location |
| How many planets are in the Solar System? | Numeric |
| What does CPU stand for? | Abbreviation |
| What is Artificial Intelligence? | Description |
| Which animal is the fastest? | Entity |

---

## Key Findings

- Linear SVM provides a strong baseline for short-text classification.
- TF-IDF features perform well but cannot capture semantic relationships.
- BERT learns contextual representations that improve classification accuracy.
- Transformer-based models significantly reduce confusion between similar question categories.

---

## Future Enhancements

- Fine-tune RoBERTa and DeBERTa models.
- Perform hyperparameter optimization.
- Deploy the model using Streamlit.
- Explore zero-shot and few-shot classification.
- Extend the system to multilingual question classification.

---

## References

- Devlin et al. (2019) — BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding.
- Cortes & Vapnik (1995) — Support Vector Networks.
- Li & Roth (2002) — Learning Question Classifiers.
- Hugging Face Transformers Library.
- Scikit-learn Documentation.

---

## Author

**Abhishek**

MSc Data Science

University of Hertfordshire

---

## License

This repository is created for academic and educational purposes.
