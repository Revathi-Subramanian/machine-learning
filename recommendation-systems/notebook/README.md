Collaborative Filtering Recommendation Engine

### Objective
To develop a robust and personalized recommendation system that suggests tourist places to users based on their historical ratings and the similarity between places.

### Methodology: Collaborative Filtering

| Feature | Details |
| :--- | :--- |
| **Data Sources** | Merged three datasets: `tourism_rating.csv`, `tourism_with_id.xlsx`, and `user.csv`. |
| **EDA Insights** | Analyzed visitor demographics (peak age: 29-31) and identified high-rated categories, confirming **Bandung** as a prime location for nature tourism. |
| **Models** | Implemented and tested two models based on centered rating matrices: **Item-Based Collaborative Filtering** and **User-Based Collaborative Filtering**. |
| **Core Technique** | Used **Cosine Similarity** to compute similarity between places (Item-Based) and between users (User-Based). |
| **Output** | Created functions to provide both location-based recommendations (for tourists visiting a current spot) and personalized recommendations (for a specific user ID). |

### Evaluation Metrics
The recommender system was evaluated using industry-standard ranking metrics:

* **Precision@k**
* **Recall@k**

##  Setup and Installation

To run this project, you will need the following libraries. It is recommended to use a virtual environment or Google Colab (as done in the notebook).

### Libraries Used
* Pandas, NumPy
* Scikit-learn (`cosine_similarity`)
* Seaborn, Matplotlib

---


