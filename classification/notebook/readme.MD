Employee Turnover Prediction and Retention Strategy – Machine Learning Project
Author: Your Name
Company: Portobello Tech (Case Study)
Domain: Human Resources Analytics / Predictive Modeling
Project Overview

Portobello Tech aims to predict employee turnover and identify the key factors driving employees to leave the organization. The HR department has collected data related to employee satisfaction, evaluations, workload, compensation, and promotion history.

As the ML developer, the objectives of this project are to:

Perform data quality checks

Analyze factors influencing employee attrition

Conduct clustering analysis on employees who left

Address class imbalance using SMOTE

Train and evaluate models using k-fold cross-validation

Select the best-performing model using GridSearchCV

Recommend retention strategies based on model insights

Dataset Description

The dataset contains 14,999 employee records with the following attributes:

Feature	Description
satisfaction_level	Employee satisfaction score (0–1)
last_evaluation	Performance evaluation score (0–1)
number_project	Number of projects completed
average_montly_hours	Average monthly hours worked
time_spend_company	Tenure in years
Work_accident	Workplace accident indicator (0/1)
promotion_last_5years	Promotion indicator (0/1)
sales	Department
salary	Salary level (low/medium/high)
left	Target variable (1 = left, 0 = stayed)
1. Data Quality Checks

Key findings:

No missing values detected

3008 duplicates removed

sales column renamed to department for clarity

Salary categories mapped to ordinal values

One-hot encoding applied to department

Dataset prepared for EDA and modeling

2. Exploratory Data Analysis (EDA)
Attrition Patterns

Sales department shows the highest turnover

Low-salary employees leave significantly more

Employees with promotions rarely leave

Long working hours and high project counts influence attrition

Behavioral Insights

High correlation between number_project and average_montly_hours

Satisfaction levels decrease slightly with tenure

Work accidents show no meaningful relationship with attrition

Satisfaction-Level Observations

Two peaks among employees who left: around 0.1 and 0.4

Some high-satisfaction employees also left, indicating non-job-related reasons

3. Clustering of Employees Who Left

K-Means clustering with k = 3 was applied using:

satisfaction_level

last_evaluation

Cluster Interpretation
Cluster	Characteristics	Interpretation
Cluster 0	Lower evaluation, moderate satisfaction	Underperformers
Cluster 1	High evaluation, low satisfaction	Unsatisfied high performers
Cluster 2	High evaluation, high satisfaction	High achievers; attrition not driven by satisfaction or performance

Silhouette Score: 0.80, indicating strong cluster separation.

4. Handling Class Imbalance (SMOTE)

Target distribution: 83% stayed, 17% left

SMOTE applied to training data to balance classes

Prevents model bias toward the majority class and improves recall for the minority class

5. Machine Learning Models and Cross-Validation

Three models were evaluated using GridSearchCV (5-fold CV):

Logistic Regression

Random Forest Classifier

Gradient Boosting Classifier

Metrics Considered

F1 Macro Score

Confusion Matrix

ROC-AUC

Precision

Recall (minimizing false negatives is critical)

Accuracy

6. Best Model: Gradient Boosting Classifier
Why This Model Was Selected

Highest ROC-AUC score

Best recall performance

Lower Type I and II errors

Strong generalization performance across CV folds

Error Interpretation

False Positives (Type I): Predicting "stay" when employee actually leaves

False Negatives (Type II): Predicting "leave" when employee stays

Minimizing Type I errors is crucial for HR to avoid unexpected attrition. Gradient Boosting provides the best balance.

7. Risk Segmentation (Probability Zoning)

Predicted probabilities were segmented into four risk zones:

Zone	Interpretation	Recommended Action
Safe (Green)	Very likely to stay	No action needed
Low-Risk (Yellow)	Slight chance of leaving	Light monitoring
Medium-Risk (Orange)	Moderate attrition likelihood	HR review recommended
High-Risk (Red)	Strong likelihood of leaving	Immediate retention action

Most employees in the high-risk zone were consistent with model predictions and demonstrated low satisfaction or high workload.

Retention Strategy Recommendations

Based on modeling and clustering outcomes:

Improve overall satisfaction through surveys and engagement programs

Reduce excessive workload and limit simultaneous projects

Encourage normal working hours and reduce chronic overtime

Prioritize timely promotions for high performers

Consider salary adjustments for low-paid employees in high-risk groups

These actions directly target the major factors contributing to attrition.

machine-learning
├── classification/
	└──	├── data/
		│   └── HR_comma_sep.csv
		├── notebook/
		│   └── employee_turnover_analysis.ipynb
			└──├── README.md


Technologies Used

Python

Pandas, NumPy

Seaborn, Matplotlib

Scikit-Learn

Imbalanced-Learn (SMOTE)

K-Means Clustering

Gradient Boosting Classifier

Conclusion

This project demonstrates a complete end-to-end machine learning workflow for HR analytics. Through EDA, clustering analysis, model tuning, and risk segmentation, we built a robust solution that enables Portobello Tech to predict employee turnover and implement targeted retention strategies.