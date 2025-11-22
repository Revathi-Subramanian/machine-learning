# Machine Learning Portfolio

This repository serves as a collection of personal Machine Learning projects, focusing on applications in traditional classification, Regression, and advanced applications in Deep Learning, Computer Vision, object detection, Recommender Systems.

---

## Project Index

| Project Name | Location | Primary Focus | Key Techniques | Status |
| :--- | :--- | :--- | :--- | :--- |
| **Tourism Structure Prediction** | [`deep-learning/classification`](deep-learning/classification/notebook/) | CV Classification | EfficientNetB0, ResNet50, EDA | Complete |
| **Tourism Recommendation System** | [`recommendation-systems/notebook`](recommendation-systems/notebook/) | Recommendation Engine | Collaborative Filtering, EDA | Complete |
| **Attrition Prediction System** | [`classification/notebook`](classification/notebook/) | Employee Turover Analysis | EDA,Clustering,SMOTE,GridSearchCV | Complete |
---
machine-learning/
├── deep-learning/
│   └── classification/
│       └── notebook/
│           └── Tourism_Structure_Prediction_Project.ipynb  (Part 1)
└── recommendation-systems/
    └── notebook/
        └── Indonesia_Tourism_Recommendation_System.ipynb  (Part 2)
└── classification/
│       └── notebook/
│           └── HRD_Emp_Turnover_Analysis.ipynb  (Attrition Prediction)
        
## Tourism Structure Prediction & Recommendation Engine

This is a dual-focus project designed to apply modern ML techniques to the cultural heritage and tourism sector. First part uses image recognition to identify structural components, 
and second, uses predictive modeling to recommend relevant tourist destinations based on user behavior and place characteristics.

### 1. Architectural Structure Classification (Part 1)
Applies **Deep Learning** and **Transfer Learning** to automatically identify 10 distinct architectural components (e.g., dome, bell tower) from images of historical sites.
Evaluated EfficientNetB0 and ResNet50 using transfer learning of Imagenet training weights

* **Model Selected:** **EfficientNetB0** (achieved 92.02% Accuracy).
* **Key Skills:** Image Cleaning (OpenCV/PIL), CNN Design, Model Benchmarking.
* **Code:** [Tourism_Structure_Prediction_Project.ipynb](deep-learning/classification/notebook/Tourism_Structure_Prediction_Project.ipynb)
* **Evaluation:** Confusion Matrix, accuracy, weighted, and macro f1 score.

### 2. Collaborative Filtering Recommendation Engine (Part 2)
Develops a system to provide personalized travel suggestions based on user ratings and place attributes.

* **Models:** Implemented **Item-Based** and **User-Based** Collaborative Filtering.
* **Insights:** Identified user demographics, top-rated categories, and the best city for nature tourism (**Bandung**).
* **Evaluation:** Assessed performance using **Precision@k** and **Recall@k**.

### 3. Employee Attrition Prediction :
Portobello Tech is an app innovator company that devised an intelligent way of predicting employee turnover within the company. It periodically evaluates employees' work details, including the number of projects they worked on, average monthly working hours, time spent in the company, promotions in the last five years, and salary level.

Data from prior evaluations shows the employees’ satisfaction in the workplace. The data could be used to identify patterns in work style and their interest in continuing to work for the company. 

The HR Department owns the data and uses it to predict employee turnover. Employee turnover refers to the total number of workers who leave a company over time.
* **Models:** Implemented classification by evaluating against **Linear Regression, Gradient Boost , Random Forest classifier** models and choosing Gradient Boost as the best model for this use case.
* **Insights:** performed clustering to identify relationship between satisfaction level and evaluation with silhoutte score of 0.8, applied SMOTE to address class imbalance in left vs stayed
* **Evaluation:** Assessed performance using **confusionmatrix** and **AUC score and accuracy score**.
---

## Setup and Technologies

This project was primarily developed in a Google Colab environment.

### Core Libraries

To run the notebooks locally, ensure you have the following installed:

```bash
!pip install tensorflow numpy pandas matplotlib seaborn scikit-learn opencv-python pillow
