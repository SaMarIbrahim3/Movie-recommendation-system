AI-Powered Movie Recommendation System

Overview
This project focuses on building a machine learning–based recommendation engine that uses **content-based filtering** and **clustering** to deliver personalized movie suggestions. The system leverages semantic similarity between movies to help users discover hidden gems beyond mainstream popularity lists.


Dataset
The dataset consists of movie metadata including:
Titles  - Genres - Overviews and descriptions - Vote counts and averages - Release dates  


Data Preprocessing
Extensive preprocessing was applied to prepare the data for modeling, including:
Handling missing values and deduplication  
Normalizing text (lowercasing, punctuation removal)  
Converting stringified lists (genres, cast, tags) into Python lists  
Extracting temporal features such as release year and recency bias  
Cleaning categorical features (e.g., adult column) using mode imputation  
Handling runtime outliers by capping extreme values and imputing with median  

Feature Engineering
Advanced feature engineering was performed to create a unified feature matrix:
TF-IDF Vectorization: Converted movie overviews into discriminative keyword vectors.  
Multi-Label Encoding: Represented multi-genre movies with binary flags.  
Feature Scaling: Standardized numeric features (vote_count, vote_average).  

PCA
High-dimensional TF-IDF vectors were compressed using Principal Component Analysis (PCA) to retain 90% of variance.  

Benefits:
Faster clustering and nearest-neighbor queries  
Reduced noise from rare tokens  
Compact, dense representations for visualization and indexing  

---

Model
Two clustering algorithms were applied:
K-Means: Efficient for balanced, spherical clusters.  
DBSCAN: Density-based clustering to uncover niche titles and flag outliers.  

Evaluation metrics included:
Silhouette Score  
Davies-Bouldin Index  
Elbow Method (Inertia)  

Results
The clustering approach successfully grouped movies into meaningful clusters, uncovering genre-dense regions and niche categories. Outliers highlighted unique or mislabeled titles. Recommendations were ranked by ratings and recency, providing curated lists of similar films.


Goal
The goal of this project is to build an intelligent recommendation engine that improves user engagement by surfacing **personalized, high-quality, and less-known movies** aligned with user preferences.


Tools & Technologies
- Python  
- Pandas & NumPy  
- Scikit-learn  
- TF-IDF  
- PCA  
- Matplotlib & Seaborn  
- Streamlit / Flask (deployment)  
