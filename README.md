
# **Interactive Medical Triage Prediction System**

## **Overview**
This project provides an **interactive medical triage prediction system** using machine learning. The system classifies patients into **Low, Medium, and High risk** categories using clinical data. It outputs a **risk score**, **color-coded triage level**, **model confidence**, and **clinical action recommendations** to assist healthcare professionals in decision-making.

## **Key Features**
- **Risk Prediction:** Classifies patients into risk levels (Low, Medium, High).
- **Risk Score Calculation:** Converts the predicted probability into a score (0-100).
- **Color-coded Triage Levels:** Green, Yellow, and Red levels for each prediction.
- **Model Confidence:** Provides a confidence score for predictions.
- **Clinical Action Recommendations:** Suggests actions (e.g., immediate attention, follow-up, routine check-up).

## **Dependencies**
- Python 3.x
- **NumPy**: For numerical computations.
- **Pandas**: For data manipulation.
- **Matplotlib**: For visualizations.
- **Scikit-learn**: For machine learning models and evaluation.
- **Imbalanced-learn (SMOTE)**: For class balancing.

## **Dataset**
The model uses the **UCI Heart Disease Dataset** which contains various patient features such as:
- **Age**
- **Sex**
- **Chest pain type**
- **Cholesterol level**
- **Max heart rate achieved**

The target variable is **risk** with values indicating Low, Medium, and High risk categories.

## **Usage**

### Step 1: Preprocessing
The dataset is cleaned by:
- Handling missing values using **SimpleImputer**.
- Scaling numerical features with **StandardScaler**.
- One-hot encoding categorical variables.

### Step 2: Model Training
Multiple machine learning models are trained, including:
- **Logistic Regression**
- **Support Vector Machine (SVM)**
- **Random Forest**
- **Naive Bayes**

The model performance is evaluated using **ROC-AUC**.

### Step 3: Calibration
The **Random Forest model** is calibrated using **Isotonic Regression** to improve the accuracy of predicted probabilities.

### Step 4: Prediction
The system takes real-time user input for clinical features and predicts the patient's risk level with associated explanations:
- **Risk Score**: From 0 to 100.
- **Color-Coded Triage Level**: Green (Low), Yellow (Moderate), Red (High).
- **Model Confidence**: Probability of the prediction being correct.
- **Clinical Action**: Suggests immediate action.

### Step 5: Sample Run
```python
predict_patient_risk()
````

#### Example Output:

```
Enter Patient Clinical Information
-----------------------------------
Enter age: 50
Enter sex (Male/Female): Male
Enter chest pain type (0–3): 1
Enter cholesterol level: 250
Enter max heart rate achieved: 170

Triage Prediction Result
---------------------------
Predicted Risk Level : High Risk
Risk Score           : 92/100
Triage Color Code    : Red (High Risk)
Model Confidence     : 0.93
Class Probabilities  : [0.05 0.02 0.93]

Recommended Action
 Immediate medical attention required
```

## **Model Details**

The system uses the **Random Forest classifier** that has been **calibrated** to improve its predicted probabilities. The model's confidence score is derived from the highest predicted probability.

## **Ethical Considerations**

* **Bias in Dataset**: The dataset may have gender and age-related biases, which are important to consider when deploying the model.
* **False Negatives**: The risk of predicting a patient as lower risk when they are actually high risk.
* **Privacy**: Patient data privacy is crucial and should be handled according to the relevant medical data protection regulations.

## **Development & Contributions**

To contribute:

1. Fork the repository.
2. Create a new branch.
3. Implement your changes.
4. Submit a pull request with a detailed description.

## **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

