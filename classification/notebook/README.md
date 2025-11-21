# Employee Turnover Prediction & Retention

## Overview
This project analyzes employee data from Portobello Tech to predict employee turnover, understand patterns behind attrition, and recommend targeted retention strategies.
It demonstrates a complete machine learning workflow including:

Data quality checks

Exploratory Data Analysis (EDA)

Clustering of employees who left

Handling class imbalance with SMOTE

Model training using GridSearchCV and cross-validation

Model comparison and selection

Business-driven recommendations

---

## Dataset
| Feature | Description |
|---------|------------|
| satisfaction_level | Employee satisfaction (0–1) |
| last_evaluation | Performance evaluation (0–1) |
| number_project | Number of projects completed |
| average_montly_hours | Monthly working hours |
| time_spend_company | Years spent at the company |
| Work_accident | Accident indicator (0/1) |
| promotion_last_5years | Promotion indicator (0/1) |
| sales | Department |
| salary | Salary (low/medium/high) |
| left | Target (1 = left, 0 = stayed) |

---

## Workflow

1. **Data Preprocessing**
   - Remove duplicates
   - Encode categorical variables
   - Standardize numerical features
   - Stratified train-test split

2. **EDA & Insights**
   - High turnover in Sales and low-salary employees
   - Promotions reduce attrition
   - More projects and longer hours → higher turnover

3. **Clustering**
   - K-Means (k=3) on satisfaction & last evaluation
   - Silhouette score = 0.8
   - Clusters: Underperformers, Unsatisfied high performers, High achievers

4. **Class Imbalance**
   - Target distribution: 17% left, 83% stayed
   - Handled using SMOTE

5. **Modeling**
   - Logistic Regression, Random Forest, Gradient Boosting
   - Hyperparameter tuning with GridSearchCV
   - Evaluation: F1, ROC-AUC, Confusion Matrix, Recall prioritized

6. **Best Model**
   - Gradient Boosting: highest ROC-AUC and recall

---

## Risk Segmentation

| Risk Zone | Action |
|-----------|--------|
| Safe Zone | No action |
| Low-Risk Zone | Monitor lightly |
| Medium-Risk Zone | HR review |
| High-Risk Zone | Immediate retention action |

---

## Retention Recommendations
- Improve satisfaction through engagement programs
- Reduce workload and excessive hours
- Promote high performers and offer incentives
- Address low-salary compensation gaps

---

## Project Structure
machine-learning
├── classification/
	└──	├── data/
		│   └── HR_comma_sep.csv
		├── notebook/
		│   └── employee_turnover_analysis.ipynb
			└──├── README.md
## Tools & Libraries

- Python, Pandas, NumPy, Matplotlib, Seaborn
- Scikit-Learn (Logistic Regression, Random Forest, Gradient Boosting)
- Imbalanced-Learn (SMOTE)
- K-Means Clustering
