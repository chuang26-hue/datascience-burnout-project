# 📊 Predicting Burnout Risk in Remote Workers

## 📌 Overview
The rise of remote and hybrid work has introduced new challenges related to employee well-being, including fatigue, social isolation, and burnout.  
This project aims to analyze behavioral and work-related data to **predict burnout risk levels (Low, Medium, High)** using machine learning techniques.

We leverage both **supervised classification models** and **unsupervised clustering methods** to not only predict burnout but also uncover meaningful behavioral patterns.

---

## 🎯 Objectives
- Predict employee burnout risk levels using behavioral data  
- Compare performance across multiple classification models  
- Identify key drivers of burnout  
- Discover latent behavioral profiles using clustering  

---

## 📂 Dataset
- Source: Work-from-home employee burnout dataset  
- Observations: ~2,000 samples  
- Features include:
  - Work hours  
  - Screen time  
  - Meetings count  
  - Sleep hours  
  - Task completion  
  - Isolation index  
  - Fatigue score  

- Target variable:
  - `burnout_risk` (Low, Medium, High)

---

## ⚙️ Methodology

### 🔹 Data Preprocessing
- Removed irrelevant identifiers (e.g., user_id)  
- One-hot encoded categorical variables  
- Standardized numerical features  
- Train-test split (80/20)  
- Addressed class imbalance using class weighting  

---

### 🔹 Supervised Learning (Classification)

We implemented three classification algorithms:

| Model                | Description |
|---------------------|------------|
| Logistic Regression | Linear baseline model |
| Random Forest       | Ensemble model capturing nonlinear patterns |
| Support Vector Machine (SVM) | Nonlinear classifier using RBF kernel |

---

### 🔹 Unsupervised Learning (Clustering)

- K-Means  
- Agglomerative Clustering  
- BIRCH  

Used to:
- Identify behavioral groupings  
- Generate employee profiles  
- Complement predictive modeling  

---

## 📊 Evaluation

### 🔹 Classification Metrics
- Accuracy  
- Precision  
- Recall  
- F1-score (Macro & Weighted)  
- Confusion Matrix  

### 🔹 Clustering Metrics
- Silhouette Score  
- Davies-Bouldin Index  
- Calinski-Harabasz Score  
- Cluster Purity  

---

## 📈 Results

### 🔹 Classification
- All models achieved **>95% accuracy**  
- Random Forest performed best overall  
- Logistic Regression provided a strong baseline  
- SVM showed comparable performance  

📌 Key Insight:  
- Most classification errors occur between **Medium and High risk**

---

### 🔹 Clustering
- K-Means produced compact clusters  
- BIRCH showed best separation (highest silhouette)  
- Agglomerative clustering aligned best with actual labels (highest purity)  

📌 Key Insight:  
- Different clustering methods optimize different aspects (compactness vs separation vs label alignment)

---

## 🧠 Key Findings
- Burnout is strongly associated with:
  - Fatigue  
  - Isolation  
  - Work hours  
  - Sleep patterns  
- Behavioral data is highly predictive of burnout risk  
- Nonlinear models provide slight improvements over linear models  
- Clustering reveals distinct employee profiles for targeted intervention  

---

## ⚠️ Limitations
- Class imbalance (few high-risk observations)  
- Synthetic dataset may not fully reflect real-world variability  
- Potential for feature leakage if not handled carefully  

---

## 🚀 Future Work
- Apply to real-world datasets  
- Incorporate time-series behavioral data  
- Improve handling of minority classes  
- Deploy as a real-time burnout monitoring tool  

---

## 📚 Related Work
- Psychological and HCI research linking burnout to behavioral patterns  
- Industry approaches using PCA and clustering for profiling  
- Kaggle study using Random Forest regression (≈57% accuracy after classification conversion)

---

## 🛠️ Tech Stack
- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib, Seaborn  

---

## 👥 Contributors
- Phoebe Huang  
- [Add teammates here]

---

## 📌 Conclusion
This project demonstrates that machine learning can effectively predict burnout risk and uncover meaningful behavioral patterns. By combining classification and clustering approaches, we provide both **predictive accuracy and actionable insights** for improving employee well-being.
