
# **Stroke Prediction Project**

## **Project Overview**
This project focuses on predicting the risk of stroke using patient data. The objective is to develop an effective machine learning model that assists healthcare professionals in identifying high-risk individuals based on various clinical and lifestyle factors.

## **Technologies Used**
- Python (Pandas, NumPy, Scikit-Learn, XGBoost, TPOT)
- Power BI (Dashboard Visualization)
- Jupyter Notebook
- Streamlit (Prototype Web Application)

## **Dataset Description**
- **Source:** Publicly available health dataset.
- **Key Features:**
  - Demographics: Age, Gender, Residence Type
  - Health Factors: Hypertension, Heart Disease, BMI, Glucose Levels
  - Lifestyle: Smoking Status, Work Type, Marital Status
- **Target Variable:** `Stroke` (0 = No, 1 = Yes)

## **Exploratory Data Analysis (EDA)**
- The dataset is highly imbalanced (only ~5% stroke cases).
- Age, hypertension, heart disease, and glucose levels are significant predictors.
- No strong multicollinearity found among features.
- Visualizations include:
  - Correlation Heatmap
  - Feature Distribution Plots
  - Class Imbalance Visualization

## **Data Preprocessing**
- Removed irrelevant `id` column.
- Imputed missing BMI values using the median.
- Handled missing values in `smoking_status` by introducing a new category `Unknown`.
- Applied One-Hot Encoding for categorical variables.
- StandardScaler used for normalizing numerical features.

## **Models Applied**
1. **Logistic Regression**
   - Accuracy: 95%
   - Stroke Recall: 2% (Poor recall due to class imbalance)
   - ROC-AUC: 0.84

2. **Random Forest Classifier**
   - Accuracy: 95%
   - Stroke Recall: 0%
   - ROC-AUC: 0.78
   - Highly biased toward the majority class.

3. **XGBoost Classifier**
   - Accuracy: ~84%
   - Stroke Recall: 18% (Improved)
   - ROC-AUC: ~0.78

4. **TPOT Optimized Pipeline**
   - Accuracy: 84%
   - Stroke Recall: 50% (Best Recall Achieved)
   - F1-Score: 0.24
   - This pipeline achieved the best balance between detecting stroke and minimizing false positives.

## **Final Model Recommendation**
- **TPOT Optimized Pipeline** was selected as the final model due to its superior recall performance, critical in medical risk prediction where missing a positive case is highly undesirable.

## **Power BI Dashboard**
- An interactive dashboard was created to visualize:
  - Class Distribution
  - Feature Importance
  - Risk Profiles based on key features like Age and Glucose Level

## **Future Enhancements**
- Implement SMOTE or other resampling techniques for further balancing the dataset.
- Try advanced ensemble models like LightGBM or CatBoost.
- Improve feature engineering with interaction terms and polynomial features.
- Deploy the model via Streamlit for real-time risk prediction.
