# Predicting Burnout Risk in Remote Workers

## Overview
The rise of remote and hybrid work has introduced new challenges related to employee well-being, including fatigue, social isolation, and burnout.  

This project analyzes behavioral data from remote workers to:
- Predict burnout risk  
- Identify key drivers of burnout  
- Uncover underlying behavioral patterns  

We combine classification, regression, and clustering to provide both predictive performance and deeper insight into how burnout develops.

---

## Objectives
- Predict burnout risk using behavioral and well-being data  
- Compare multiple machine learning classification models  
- Identify the strongest drivers of burnout intensity  
- Discover latent employee profiles using clustering  
- Evaluate how well-being vs. work patterns explain burnout  

---

## Dataset
- Source: Kaggle (synthetic work-from-home dataset)  
- Observations: ~2,000  

### Features
- Work hours  
- Screen time  
- Meetings count  
- Sleep hours  
- Task completion  
- Isolation index  
- Fatigue score  
- App switching behavior  
- Day type (weekday/weekend)  

### Target Variable
- Original: `burnout_risk` (Low, Medium, High)  
- Transformed into binary classification:
  - `Low` → 0  
  - `Medium`, `High` → 1 (At Risk)  

This transformation helps address class imbalance and improves model stability.

---

## Methodology

### Data Preprocessing
- Removed irrelevant columns (e.g., `user_id`)  
- One-hot encoded categorical variables  
- Standardized numerical features (for Logistic Regression & SVM)  
- Train-test split (80/20)  
- Addressed class imbalance using class weights  
- Removed leakage features (`burnout_score`, `fatigue_score`)  

---

## Modeling

### Classification (Primary Task)

| Model                | Description |
|---------------------|------------|
| Logistic Regression | Baseline linear model with class weighting |
| Random Forest       | Ensemble model capturing nonlinear relationships |
| SVM (RBF Kernel)    | Nonlinear classifier using kernel trick |

---

### Regression (Estimation)
Used to understand burnout intensity:

- OLS Regression:
  - Work-pattern variables → ~50% variance explained  
  - Well-being variables → ~98% variance explained  

- Machine Learning:
  - Linear Regression (baseline)  
  - Random Forest Regressor (better performance)

---

### Clustering (Behavioral Profiling)

Models:
- K-Means  
- Agglomerative Clustering  
- BIRCH  

Purpose:
- Identify employee behavioral profiles  
- Understand burnout as a spectrum  

---

## Evaluation

### Classification Metrics
- Accuracy  
- Precision  
- Recall  
- F1-score (macro emphasized)  

### Baseline
- Majority class classifier ≈ 51% accuracy  

### Clustering Metrics
- Silhouette Score  
- Davies-Bouldin Index  
- Calinski-Harabasz Score  
- Cluster Purity  

---

## Results

### Classification
- Logistic Regression: ~95% accuracy  
- Random Forest: ~94% accuracy  
- SVM: ~96% accuracy (best)  

Key Insight:
- High performance only after removing leakage variables  

---

### Regression
- Well-being variables explain significantly more burnout variation than work patterns  
- Burnout is driven more by recovery and psychological factors than workload alone  

---

### Clustering
- Three behavioral groups consistently emerge:
  - Low burnout  
  - Moderate burnout  
  - High strain  

However:
- Low silhouette scores indicate overlapping groups  
- Burnout behaves as a continuous spectrum  

---

## Key Findings
- Burnout is strongly associated with:
  - Fatigue  
  - Isolation  
  - Sleep patterns  
  - Work intensity  

- Behavioral data is highly predictive  
- Nonlinear models provide slight improvements  
- Well-being factors are more important than workload alone  

---

## Limitations
- Synthetic dataset may exaggerate relationships and inflate performance  
- Class imbalance in original labels  
- Risk of feature leakage if not handled carefully  
- Real-world data would likely be noisier  

---

## Future Work
- Validate on real-world datasets  
- Incorporate time-series behavioral data  
- Improve modeling of high-risk cases  
- Build real-time burnout monitoring systems  
- Add features like team dynamics and managerial support  

---

## Ethical Considerations
- Models should support—not penalize—employees  
- Ensure transparency and fairness  
- Use predictions for intervention, not surveillance  

---

## Tech Stack
- Python  
- Pandas, NumPy  
- Scikit-learn  
- Statsmodels  
- Matplotlib, Seaborn  

---

## Contributors
- Phoebe Huang  
- Isabel Ojeda  
- Daniel Huss  
- Christian Dunne  

---

## Repository
https://github.com/chuang26-hue/datascience-burnout-project  

---

## Conclusion
This project demonstrates that burnout can be effectively predicted and analyzed using behavioral data. By combining classification, regression, and clustering, we provide both predictive accuracy and actionable insights for improving employee well-being.
