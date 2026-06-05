# 🚢 Titanic Survival Prediction - Machine Learning Learning Project

## 📌 Project Overview

This project explores the famous Titanic dataset and demonstrates a complete Machine Learning workflow, from understanding the dataset to building and evaluating a classification model.

The goal is to predict whether a passenger survived the Titanic disaster using passenger information such as age, gender, ticket fare, passenger class, and family details.

This project was built as a learning exercise to understand:

- Data Cleaning
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Logistic Regression
- Confusion Matrix
- Accuracy, Precision, Recall, F1 Score
- Cross Validation

---

## 🎯 Objective

Predict:

- **0 = Did Not Survive**
- **1 = Survived**

using passenger information from the Titanic dataset.

---

## 📂 Dataset Information

**Dataset:** Titanic Dataset (Kaggle)

### Features Used

| Feature | Description |
|----------|------------|
| Pclass | Passenger Class |
| Sex | Gender of Passenger |
| Age | Age of Passenger |
| SibSp | Number of Siblings/Spouses aboard |
| Parch | Number of Parents/Children aboard |
| Fare | Ticket Fare |
| Embarked | Port of Embarkation |

### Target Variable

`Survived`

---

## 🧹 Data Preprocessing

### Missing Values Found

- Age
- Cabin
- Embarked

### Handling Strategy

#### Age

Missing values filled using the **Median**.

#### Embarked

Missing values filled using the **Mode**.

#### Cabin

Dropped because more than **75% of values were missing**.

---

## 🔄 Feature Engineering

### Removed Columns

The following columns were removed because they were not useful for prediction:

- PassengerId
- Name
- Ticket
- Cabin

### Encoding

#### Sex

| Original | Encoded |
|-----------|---------|
| Male | 0 |
| Female | 1 |

#### Embarked

Applied One-Hot Encoding using:

```python
pd.get_dummies()
```

---

## 📊 Exploratory Data Analysis (EDA)

Several visualizations were created to understand the dataset.

### 1. Survival Distribution

**Observation:**

More passengers died than survived.

---

### 2. Survival by Gender

**Observation:**

Female passengers had significantly higher survival rates.

**Insight:**

Gender is one of the strongest predictors of survival.

---

### 3. Survival by Passenger Class

**Observation:**

1st Class > 2nd Class > 3rd Class

in terms of survival probability.

**Insight:**

Passenger class strongly influences survival.

---

### 4. Fare vs Survival

**Observation:**

Passengers paying higher fares were more likely to survive.

**Insight:**

Fare has a positive relationship with survival.

---

### 5. Correlation Heatmap

**Key Findings:**

- Sex → Strongest positive correlation with survival
- Pclass → Negative correlation with survival
- Fare → Positive correlation with survival
- Age → Weak correlation with survival

---

## 🤖 Model Building

### Model Used

```python
LogisticRegression()
```

### Why Logistic Regression?

- Simple baseline model
- Easy to interpret
- Suitable for binary classification problems
- Fast to train

---

## ✂️ Train-Test Split

Dataset was divided into:

- **80% Training Data**
- **20% Testing Data**

using:

```python
train_test_split()
```

### Why?

To train the model on one portion of data and evaluate it on unseen data.

---

## 📈 Model Evaluation

### Confusion Matrix

```text
[[90 15]
 [19 55]]
```

Where:

```text
TN = 90
FP = 15
FN = 19
TP = 55
```

### Metrics Learned

#### Accuracy

Measures overall correctness of the model.

#### Precision

Measures how many predicted positives were actually positive.

#### Recall

Measures how many actual positives were correctly identified.

#### F1 Score

Balances Precision and Recall into a single metric.

---

## 🔄 Cross Validation

Used **5-Fold Cross Validation** to obtain a more reliable estimate of model performance.

### Benefits

- Reduces dependency on a single train-test split
- Provides a more robust performance estimate
- Helps detect model instability

---

## 📚 Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.model_selection import train_test_split
from sklearn.model_selection import cross_val_score

from sklearn.linear_model import LogisticRegression

from sklearn.metrics import (
    confusion_matrix,
    accuracy_score,
    classification_report
)
```

---

## 🚀 Machine Learning Workflow Followed

```text
Dataset
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
EDA
   ↓
Train-Test Split
   ↓
Model Training
   ↓
Prediction
   ↓
Confusion Matrix
   ↓
Accuracy / Precision / Recall / F1 Score
   ↓
Cross Validation
```

---

## 💡 Key Learnings

- Data understanding is as important as model building.
- EDA helps uncover patterns before training models.
- Confusion Matrix provides deeper insights than accuracy alone.
- Precision, Recall, and F1 Score are critical evaluation metrics.
- Cross Validation provides a more reliable estimate of model performance.
- Machine Learning is not just about training models; it is about understanding data and making informed decisions.

---

## 🔗 Repository

GitHub Repository:

https://github.com/kartik-bissa/ML1

---

## 👨‍💻 Author

**Kartik Bissa**

Learning Machine Learning through hands-on projects, data exploration, visualization, and practical implementation.

🚀 Always learning, always building.
