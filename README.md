# StreamFlex: Customer Churn Prediction

Predicting customer churn for a subscription service using Decision Tree and Random Forest classifiers. 

## 📌 Project Overview
[cite_start]The objective of this project is to identify customers who are at a high risk of canceling their StreamFlex subscription before they actually leave[cite: 28, 29]. [cite_start]By effectively predicting churn, the business can proactively address customer dissatisfaction, design targeted marketing strategies, and prioritize retention efforts based on data-driven insights[cite: 29, 32, 39]. 

[cite_start]Decision trees and random forests were chosen for their strong analytical power, ability to handle mixed data types without linearity assumptions, and high interpretability for non-technical stakeholders[cite: 14, 16, 19, 21].

## 📊 Dataset & Preprocessing
[cite_start]The dataset consists of 1,000 customer records and 12 features, including demographic data, behavioural trends, and service-related metrics[cite: 184, 186].
* [cite_start]**Data Quality:** The dataset contained no missing values or duplicate records[cite: 41]. 
* [cite_start]**Feature Engineering:** * `CustomerID` was dropped as it provided no predictive value[cite: 46].
  * [cite_start]Continuous numerical variables like `Age` and `Watch_Time_Hours` were grouped into ordered categories to improve interpretability[cite: 44].
  * [cite_start]Categorical variables (`Payment_Method`, `Preferred_Content_Type`, `Membership_Type`) were encoded into numerical labels to ensure compatibility with scikit-learn[cite: 45].
* [cite_start]**Data Splitting:** The data was split into training (70%) and testing (30%) sets using `train_test_split`[cite: 47].

## ⚙️ Methodology & Modeling
Two tree-based classification models were trained and evaluated:
1. [cite_start]**Decision Tree Classifier:** Acts as a highly interpretable "white-box" model that segments data using intuitive "if-then" logic[cite: 21, 25].
2. [cite_start]**Random Forest Classifier:** An ensemble method used to capture broader interactions across features and reduce model variance[cite: 115, 164].

[cite_start]**Hyperparameter Tuning:** Both models were optimized using `GridSearchCV` with 5-fold cross-validation[cite: 50, 59]. [cite_start]Hyperparameters explored included `max_depth`, `min_samples_split`, and `max_features`[cite: 51, 58].

## 🚀 Results & Evaluation
[cite_start]Because the churn dataset is imbalanced, metrics beyond accuracy—such as precision, recall, and F1-score—were computed to provide a complete view of model performance[cite: 56, 218].

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| **Decision Tree** | [cite_start]0.850 [cite: 99] | [cite_start]0.878 [cite: 99] | [cite_start]0.941 [cite: 99] | [cite_start]0.909 [cite: 99] |
| **Random Forest** | [cite_start]0.843 [cite: 99] | [cite_start]0.860 [cite: 99] | [cite_start]0.958 [cite: 99] | [cite_start]0.907 [cite: 99] |

* [cite_start]**Model Comparison:** Both models performed similarly, but the Random Forest achieved a higher recall (95.8%)[cite: 100, 101]. [cite_start]In a business context, failing to identify a churner results in lost revenue, making the Random Forest's higher recall a slight practical advantage[cite: 102, 103].
* [cite_start]**Feature Importance:** Across Gini Index, Information Gain, and model feature importances, the primary drivers of churn were consistently identified as `Number_of_Complaints`, `Resolution_Time_Days`, `Payment_Issues`, and `Membership_Type`[cite: 105, 106, 233].

## 💡 Business Insights & Recommendations
[cite_start]The analysis revealed that operational and service-related factors are the main causes of customer attrition, rather than demographic traits[cite: 232]. Based on the models, StreamFlex should implement the following strategies:

1. [cite_start]**Enhance Customer Support:** Customer dissatisfaction is the strongest churn driver[cite: 234]. [cite_start]StreamFlex must prioritize lowering the number of complaints and expediting resolution times through proactive monitoring or automated ticket routing[cite: 243].
2. [cite_start]**Reduce Payment Friction:** High churn rates are associated with billing problems[cite: 238]. [cite_start]Optimizing the billing system with automatic failure notifications and flexible payment options can significantly decrease transactional barriers[cite: 245, 246].
3. [cite_start]**Reevaluate Membership Tiers:** Since attrition differs heavily within membership categories, StreamFlex should assess its pricing and perceived value, potentially introducing bundled perks or tailored content recommendations[cite: 247, 248, 249].

## 🛠️ Technologies Used
* **Language:** Python
* **Libraries:** scikit-learn, pandas, matplotlib, seaborn, numpy
* **Environment:** Jupyter Notebook
