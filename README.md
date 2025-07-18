# 🧠 Personality Classification Using Machine Learning (Introvert vs Extrovert)

### Based on CRISP-DM Methodology

---

## 📌 1. Business Understanding

The goal of this project is to **predict a person's personality type**—either **Introvert** or **Extrovert**—based on behavioral indicators. This can be useful for applications in education, recruitment, mental health, or social networking, where understanding someone's personality helps in personalization or support.

---

## 📊 2. Data Understanding

### Dataset:

* Source: `personality_dataset.csv` (included in the notebook directory)
* Shape: `2,900 rows × 8 columns`
* Target Variable: `Personality` (Introvert/Extrovert)

### Features:

| Feature                     | Type        | Description            |
| --------------------------- | ----------- | ---------------------- |
| Time\_spent\_Alone          | Numeric     | Hours per week alone   |
| Stage\_fear                 | Categorical | Yes/No                 |
| Social\_event\_attendance   | Numeric     | Frequency score        |
| Going\_outside              | Numeric     | Days per week          |
| Drained\_after\_socializing | Categorical | Yes/No                 |
| Friends\_circle\_size       | Numeric     | Count of close friends |
| Post\_frequency             | Numeric     | Social media activity  |
| Personality                 | Categorical | Target label           |

### Observations:

* Some features contain missing values.
* Mix of categorical and numeric data.
* Personality labels are well balanced.

---

## 🧹 3. Data Preparation

* **Missing Value Handling**: `SimpleImputer` used for both numeric and categorical columns.
* **Label Encoding**: Applied to convert categorical values like `Yes/No` to binary.
* **Feature Scaling**: StandardScaler applied to normalize numeric features.
* **Balancing Classes**: SMOTE (Synthetic Minority Oversampling Technique) used to handle class imbalance.

---

## 🤖 4. Modeling

Multiple classification models were evaluated:

* Logistic Regression
* Decision Tree
* Random Forest
* K-Nearest Neighbors
* Support Vector Machine (SVC)
* Gradient Boosting
* XGBoost
* **Stacking Classifier** (final model)

**Hyperparameter Tuning**: Used `RandomizedSearchCV` and `StratifiedKFold` cross-validation.

---

## 📈 5. Evaluation

### Metrics Used:

* Accuracy, F1 Score
* Confusion Matrix
* ROC-AUC Score

### Explainability:

* SHAP (SHapley Additive exPlanations) used to visualize and interpret model decisions.

---

## 🚀 6. Deployment / Next Steps

* Export model using `joblib` (optional)
* Deploy via a web app (e.g., Streamlit or Flask)
* Integrate a user input form to predict personality type in real time
* Explore more features such as hobbies, media consumption, or survey data

---