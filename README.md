## 🧠 Personality Prediction using Machine Learning (XGBoost)

### 📘 Project Overview

This project aims to classify individuals as **Introvert** or **Extrovert** based on their behavioral survey data using an XGBoost classification model. The process follows the **CRISP-DM** framework.

---

## 🔁 CRISP-DM Framework

### 1. **Business Understanding**

* **Objective**: Predict an individual's personality type (Introvert or Extrovert) from behavioral features.
* **Use Case**: Applicable in HR personality screening, self-assessment tools, or social media behavior analysis.

---

### 2. **Data Understanding**

* **Source**: `personality_dataset.csv`
https://www.kaggle.com/datasets/rakeshkapilavai/extrovert-vs-introvert-behavior-data

* **Records**: 2,900 entries


#### 🧾 Feature Descriptions:
| Feature | Description |
|--------|-------------|
| `Time_spent_Alone` | Hours spent alone daily (0–11). Introverts tend to have higher values. |
| `Stage_fear` | Presence of stage fright (Yes/No). Introverts are more likely to say "Yes". |
| `Social_event_attendance` | Frequency of attending events (0–10). Extroverts are typically more active. |
| `Going_outside` | Days per week one goes outside (0–7). Extroverts often go out more. |
| `Drained_after_socializing` | Feeling tired after socializing (Yes/No). Common among introverts. |
| `Friends_circle_size` | Number of close friends (0–15). Extroverts tend to have larger circles. |
| `Post_frequency` | Frequency of posting on social media (0–10). Extroverts are often more expressive. |
| `Personality` | Target label: Introvert or Extrovert. |

---

* **Initial Insights**:

  * Balanced class distribution (Introvert \~48%, Extrovert \~52%)
  * Some features have missing values

---

### 3. **Data Preparation**

* **Missing Values**:

  * Numerical columns imputed using `SimpleImputer(strategy='mean')`
* **Encoding**:

  * Categorical columns (`Stage_fear`, `Drained_after_socializing`) encoded using `LabelEncoder`
  * Target `Personality` also encoded for classification
* **Scaling**:

  * Applied `StandardScaler` to numeric features for optimal model performance
* **EDA**:

  * Correlation heatmap
  * Countplots
  * Pairplot by class

---

### 4. **Modeling**

* **Algorithm**: `XGBClassifier` (XGBoost)
* **Train-Test Split**: 80% training, 20% testing
* **Metrics**:

  * Accuracy: \~92%
  * F1-score: 0.91–0.92 for both classes
  * Confusion matrix
* **Visualization**:

  * Confusion Matrix (Seaborn heatmap)
  * Feature Importance (XGBoost’s plot\_importance)

---

### 5. **Evaluation**

* **Model performs well** on both classes with high precision and recall
* Most influential features: `Friends_circle_size`, `Social_event_attendance`, `Time_spent_Alone`
* Robust performance across metrics and data balance

---

### 6. **Deployment**

* Included code for making predictions from new questionnaire input
* Model accepts input in the form of a Python dictionary and returns predicted personality type
* Can be extended for Streamlit or web-based integration

---

## ▶️ How to Use

```python
# Example Input
sample_input = {
    'Time_spent_Alone': 5.0,
    'Stage_fear': 'Yes',
    'Social_event_attendance': 3.0,
    'Going_outside': 4.0,
    'Drained_after_socializing': 'Yes',
    'Friends_circle_size': 2.0,
    'Post_frequency': 1.0
}
```

```bash
# Run notebook: bhv_updated.ipynb
# Output: 🔮 ผลการทำนาย: บุคลิกภาพของคุณคือ --> Introvert / Extrovert
```