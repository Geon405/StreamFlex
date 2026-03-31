# StreamFlex: Customer Churn Prediction

Predicting customer churn for a subscription service using Decision Tree and Random Forest classifiers. 

## 📌 Project Overview
The objective of this project is to identify customers who are at a high risk of canceling their StreamFlex subscription before they actually leave. By effectively predicting churn, the business can proactively address customer dissatisfaction, design targeted marketing strategies, and prioritize retention efforts based on data-driven insights. 

Decision trees and random forests were chosen for their strong analytical power, ability to handle mixed data types without linearity assumptions, and high interpretability for non-technical stakeholders.

## 📊 Dataset & Preprocessing
The dataset consists of 1,000 customer records and 12 features, including demographic data, behavioural trends, and service-related metrics.
* **Data Quality:** The dataset contained no missing values or duplicate records. 
* **Feature Engineering:** * `CustomerID` was dropped as it provided no predictive value.
  * Continuous numerical variables like `Age` and `Watch_Time_Hours` were grouped into ordered categories to improve interpretability.
  * Categorical variables (`Payment_Method`, `Preferred_Content_Type`, `Membership_Type`) were encoded into numerical labels to ensure compatibility with scikit-learn.
* **Data Splitting:** The data was split into training (70%) and testing (30%) sets using `train_test_split`.

## ⚙️ Methodology & Modeling
Two tree-based classification models were trained and evaluated:
1. **Decision Tree Classifier:** Acts as a highly interpretable "white-box" model that segments data using intuitive "if-then" logic.
2. **Random Forest Classifier:** An ensemble method used to capture broader interactions across features and reduce model variance.

**Hyperparameter Tuning:** Both models were optimized using `GridSearchCV` with 5-fold cross-validation. Hyperparameters explored included `max_depth`, `min_samples_split`, and `max_features`.

## 🚀 Results & Evaluation
Because the churn dataset is imbalanced, metrics beyond accuracy—such as precision, recall, and F1-score—were computed to provide a complete view of model performance.

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **Decision Tree** | 0.850 | 0.878 | 0.941 | 0.909 |
| **Random Forest** | 0.843 | 0.860 | 0.958 | 0.907 |

* **Model Comparison:** Both models performed similarly, but the Random Forest achieved a higher recall (95.8%). In a business context, failing to identify a churner results in lost revenue, making the Random Forest's higher recall a slight practical advantage.
* **Feature Importance:** Across Gini Index, Information Gain, and model feature importances, the primary drivers of churn were consistently identified as `Number_of_Complaints`, `Resolution_Time_Days`, `Payment_Issues`, and `Membership_Type`.

## 💡 Business Insights & Recommendations
The analysis revealed that operational and service-related factors are the main causes of customer attrition, rather than demographic traits. Based on the models, StreamFlex should implement the following strategies:

1. **Enhance Customer Support:** Customer dissatisfaction is the strongest churn driver. StreamFlex must prioritize lowering the number of complaints and expediting resolution times through proactive monitoring or automated ticket routing.
2. **Reduce Payment Friction:** High churn rates are associated with billing problems. Optimizing the billing system with automatic failure notifications and flexible payment options can significantly decrease transactional barriers.
3. **Reevaluate Membership Tiers:** Since attrition differs heavily within membership categories, StreamFlex should assess its pricing and perceived value, potentially introducing bundled perks or tailored content recommendations.

## 🛠️ Technologies Used
* **Language:** Python
* **Libraries:** scikit-learn, pandas, matplotlib, seaborn, numpy
* **Environment:** Jupyter Notebook
