
#  Patient Condition Classification & Drug Recommendation System (NLP)

##  Overview

This project focuses on building an **end-to-end Natural Language Processing (NLP) pipeline** to classify patient medical conditions from drug reviews and provide **sentiment-based drug recommendations**.

The system predicts:

*  **Patient condition** (Depression, Type 2 Diabetes, High Blood Pressure)
*  **Sentiment** (Positive / Negative)
*  **Alternative drugs** (if dissatisfaction is detected)

---

##  Business Objective

* Predict patient condition from textual drug reviews
* Analyze sentiment to understand treatment effectiveness
* Recommend **alternative medications** for negative experiences
* Support patient-centric insights using data-driven methods 

---

##  Project Pipeline

```text
Raw Drug Reviews
        ↓
Text Preprocessing (NLTK, Lemmatization)
        ↓
EDA & Feature Engineering (TF-IDF, N-grams)
        ↓
Model Training (ML + Deep Learning)
        ↓
Condition + Sentiment Prediction
        ↓
Drug Recommendation (if negative)
        ↓
Flask Web Deployment
```

---

##  Data Preprocessing

* Text cleaning using **NLTK**
* Lemmatization for normalization
* Handled:

  *  899 null values
  *  noisy text (slang, spelling errors, random inputs)
* Filtered dataset to focus on:

  * Depression
  * Type 2 Diabetes
  * High Blood Pressure 

---

##  Exploratory Data Analysis (EDA)

### Key Insights:

* **Depression** had the highest number of reviews
* Majority of reviews were **positive (~9700 vs ~4300 negative)**
* Most reviews ranged between **20–80 words**
* Common words: *“day”, “week”, “mg”, “taking”*
* Drug trends:

  * Most reviewed: **Bupropion, Sertraline, Venlafaxine**

### Observations:

* Positive and negative reviews had **similar lengths**
* Language overlap caused classification challenges between conditions 

---

##  Feature Engineering

* **TF-IDF vectorization**
* **N-gram modeling** (bi-grams, tri-grams)
* **Word frequency analysis**
* **Word clouds & count vectorization**

### Insights:

* Positive reviews → treatment success, improvement
* Negative reviews → dosage concerns, inefficacy, dissatisfaction 

---

##  Model Development

### Models Implemented:

* Logistic Regression
* Naive Bayes
* Passive Aggressive Classifier
* Support Vector Machine (SVM)
* BERT (Transformer-based model)

---

##  Model Performance

| Model               | Accuracy          |
| ------------------- | ----------------- |
| Logistic Regression | 94.76%            |
| Naive Bayes         | 94.0%             |
| Passive Aggressive  | 95.0%             |
| SVM                 | 95.73%            |
| **BERT**            | **96.55% (Best)** |

### Key Observations:

* **Depression** → highest accuracy across all models
* **Diabetes** → stable and consistent performance
* **High BP** → most challenging (overlap with Depression)
* BERT achieved best performance but had high computational cost 

---

##  Challenges & Solutions

### 1️ Large Training Time (BERT)

**Problem:**

* Training took ~14 hours
* Frequent crashes due to memory limits

**Solution:**

* Migrated to **Google Colab (GPU support)**
* Reduced training time to ~4 hours

---

### 2️ Dependency Issues

**Problem:**

* TensorFlow compatibility issues

**Solution:**

* Switched to **PyTorch + Hugging Face Transformers**

---

### 3️ Multi-Task Prediction

**Problem:**

* Needed to predict both condition + sentiment

**Solution:**

* Built **two separate models** and combined outputs

---

### 4️ Deployment Integration

**Problem:**

* Difficulty integrating ML with Flask

**Solution:**

* Loaded models once at app startup for fast predictions 

---

##  Deployment

* Framework: **Flask**
* Input: Patient drug review
* Output:

  * Predicted condition
  * Sentiment
  * Alternative drug (if negative)

---

##  Tech Stack

* **Programming:** Python
* **Libraries:**

  * NLTK, Scikit-learn
  * PyTorch, TensorFlow, Keras
  * Hugging Face Transformers (BERT)
* **Deployment:** Flask
* **Tools:** VS Code

---

## Key Takeaways

* NLP can effectively extract **clinical insights from unstructured text**
* Transformer models (BERT) outperform classical ML but require more resources
* Simpler models like **SVM offer strong performance with efficiency**
* Combining sentiment + condition prediction improves real-world applicability

---

##  Limitations

* Limited to 3 conditions
* Class overlap affects recall (especially High BP)
* No real clinical validation

---

##  Future Work

* Expand to **multi-condition classification**
* Integrate **medical knowledge graphs**
* Improve recall for minority/confusing classes
* Deploy as a **clinical decision-support tool**

---

##  Author

Smrithi R
Data Science | NLP | Healthcare AI

---


