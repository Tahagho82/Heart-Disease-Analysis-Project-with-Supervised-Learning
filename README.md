# ❤️ Heart Disease Analysis Project

## 🔍 Introduction

This project explores, visualizes, and models **heart disease data**.
**Objectives:**

* Analyze clinical features such as age, gender, chest pain type, blood pressure, cholesterol, etc.
* Identify relationships between features and heart disease
* Build machine learning models to **detect patients at risk** 💓

> ⚠️ Correctly identifying patients is critical — **even a single missed case can have serious consequences**.

The dataset (`heart.csv`) contains records of both patients and healthy individuals.

---

## 📂 Project Structure

**Libraries Used:**

* `pandas`, `numpy` → Data manipulation & analysis
* `matplotlib`, `seaborn` → Data visualization
* `scikit-learn` → Preprocessing, model training, evaluation

**Project Workflow:**

1. Load the dataset
2. Perform Exploratory Data Analysis (EDA) 🔎
3. Visualize key features 📊
4. Train multiple machine learning models 🤖
5. Evaluate & compare model performance 🏆
6. Draw insights & conclusions 💡

---

## 📊 Exploratory Data Analysis (EDA)

**Key Highlights:**

* ✅ No missing values
* Balanced target variable (`target`) — patients (1) vs healthy (0)
* Features strongly correlated with heart disease:

  * Gender 👨‍👩‍👧
  * Chest pain type (`cp`) 💔
* Other contributing features:

  * Resting blood pressure (`trestbps`)
  * Cholesterol (`chol`)
  * Fasting blood sugar (`fbs`)

---

## 🤖 Machine Learning Models & Human Impact

**Dataset Split:** 80% Training, 20% Testing
**Standardization:** Features scaled using `StandardScaler`

> ⚠️ **False Negatives (FN)** = patients incorrectly predicted as healthy → **critical in healthcare** 💔

| Model                       | Accuracy | Precision | Recall (Sensitivity) | F1-score | FN (Missed Patients) |
| --------------------------- | -------- | --------- | -------------------- | -------- | -------------------- |
| SVM (RBF kernel)            | 85.25%   | 80%       | 96.97%               | 87.72%   | 1 💔                 |
| Decision Tree (max depth=5) | 81.97%   | 75%       | 100%                 | 85.71%   | 0 ✅                  |
| Naive Bayes                 | 81.97%   | 78.95%    | 90.91%               | 84.51%   | 3 💔💔💔             |
| KNN (k=7)                   | 81.97%   | 78.95%    | 90.91%               | 84.51%   | 3 💔💔💔             |
| Logistic Regression         | 80.33%   | 76.92%    | 90.91%               | 83.33%   | 3 💔💔💔             |

---

### 💡 Key Insights

* **SVM:** Highest overall accuracy but **1 patient missed**
* **Decision Tree:** Slightly lower accuracy but **0 patients missed** ✅ → safest model for patient detection
* **Naive Bayes, KNN, Logistic Regression:** Each **missed 3 patients** 💔 → higher real-world risk
* **Takeaway:** In healthcare, **minimizing false negatives can be more important than maximizing overall accuracy**
