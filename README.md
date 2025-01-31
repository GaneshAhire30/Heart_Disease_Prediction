# Heart_Disease_Prediction
 Heart disease involves conditions like coronary artery disease and arrhythmias, often linked to high blood pressure, cholesterol, and lifestyle factors.
![image](https://github.com/user-attachments/assets/07c07f35-9bc6-4c55-ab36-3dbbe13038d4)

## Project Overview
This project aims to predict the likelihood of heart disease in patients based on various medical parameters. The dataset includes multiple features such as age, cholesterol levels, blood pressure, and exercise-induced angina, among others. The goal is to build a model that optimizes recall since it is crucial in medical diagnosis to minimize false negatives.

## Dataset Information
- **Target Variable**: heart_disease (0: No Disease, 1: Disease Present)
- **Total Records**: 180
- **Total Features**: 13 (after preprocessing)

### Features Used
- sop
- thal
- resting_bp
- cpt
- major_vessels
- fasting_blood_sugar
- ekg_result
- serum_cholesterol
- oldpeak_st_depression
- sex
- age
- max_heart_rate
- exercise_induced_angina

## Exploratory Data Analysis (EDA)
- Checked for missing values, unique values, and duplicates.
- No constant columns were present.
- The dataset was balanced, with 100 instances labeled as 0 and 80 as 1.
- Correlation analysis showed no highly correlated features.

## Data Preprocessing
1. **Feature Scaling**
   - StandardScaler was applied to numerical features: resting_bp, serum_cholesterol, oldpeak_st_depression, age, max_heart_rate.
   - Standard scaling helps normalize features measured in different units.
2. **Feature Selection**
   - Dropped patient_id as it was unique for all records.
   - No highly correlated features were removed.
3. **Train-Test Split**
   - Split the dataset into 80% training and 20% testing.

## Model Selection
Four machine learning models were evaluated:
1. **Logistic Regression**
2. **K-Nearest Neighbors (KNN)**
3. **Random Forest Classifier**
4. **XGBoost Classifier**

### Performance Metrics
The models were evaluated based on **accuracy** and **recall**, with recall being the priority metric.

#### Logistic Regression
- **Training Accuracy**: 84.72%
- **Testing Accuracy**: 83.33%
- **Recall Score**: 87.5%
- After applying **Bagging**, recall improved to **88.88%**.

#### K-Nearest Neighbors (KNN)
- **Training Accuracy**: 88.19%
- **Testing Accuracy**: 80.55%
- **Recall Score**: 72.72%

#### Random Forest Classifier
- **Training Accuracy**: 100%
- **Testing Accuracy**: 83.33%
- **Recall Score (After Hyperparameter Tuning)**: 80.0%

#### XGBoost Classifier
- **Training Accuracy**: 100%
- **Testing Accuracy**: 77.77%
- **Recall Score (After Hyperparameter Tuning)**: 87.5%

## Model Selection
- The **Logistic Regression model** was chosen because it performed well on both training and testing data, with a high recall score.
- **Bagging** further improved the recall score, making it the best choice for this task.

## Model Deployment
The final Logistic Regression model was saved using **Pickle**:
python
import pickle

file = open("Logistic_regression_model.pkl", "wb")
pickle.dump(log_model, file)
file.close()


## Conclusion
- Logistic Regression is the best model for heart disease prediction.
- It maintains a good balance between accuracy and recall.
- Future improvements could include feature engineering, ensemble methods, or deep learning models.

---

This project serves as a baseline model for predicting heart disease, with potential real-world applications in healthcare diagnostics.
