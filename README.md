# Heart-Disease-Identification-Using-Ensemble-Modals
**Ali Gohar**  
**Artificial Intelligence**  
**Ghulam Ishaq Khan Institute of Science and Technology**  
**Topi, Pakistan**  
**u2022081@giki.edu.pk**

---

## Abstract
Cardiovascular illness is one of the world’s leading causes of death, and both prevention and treatment depend on early identification and precise diagnosis. In order to increase prediction accuracy and offer insights into important heart disease contributing factors, this effort builds machine learning models for evaluating people’s heart disease status using the UCI Heart Disease dataset. Additionally, this process uses group learning techniques.

**Index Terms**: Classification, Machine Learning, Ensemble Learning, Heart Disease, UCI Dataset.

---

## I. Introduction

A major cause of death and morbidity, cardiovascular diseases (CVDs) continue to be a major global health concern. The World Health Organization (WHO) reports that cardiovascular diseases (CVDs) are the world’s leading cause of death, accounting for 32% of all fatalities and 17.9 million deaths annually [1]. These problems include coronary artery disease, heart failure, arrhythmias, and other heart and blood vessel disorders. Ageing populations, genetic predispositions, and bad lifestyle choices are some of the reasons contributing to the rising prevalence of CVDs.

Reducing the impact of heart issues requires early detection and prompt action. Research indicates that prompt diagnosis enhances patient outcomes by facilitating more targeted treatment and preventative actions [2]. However, traditional diagnostic approaches depend on invasive procedures or clinical skill, limiting their effectiveness and accessibility. Innovative, data-driven methods are necessary to improve the precision and effectiveness of heart disease detection.

Machine learning (ML) has revolutionized the medical field because it can evaluate vast amounts of complex data and spot patterns that are hard for humans to see. Ensemble machine learning approaches, such as Random Forest, Gradient Boosting Machines, and XGBoost, have demonstrated exceptional effectiveness in classification problems, making them ideal for medical diagnostics [3, 4].

This study explores the application of ensemble learning techniques for heart disease classification using the UCI Heart Disease dataset. This dataset contains various patient data, including clinical, diagnostic, and demographic features. The main contributions of this paper are:

1. Analyzing the UCI Heart Disease dataset to identify important features affecting heart disease.
2. Building ensemble machine learning models and evaluating their performance against traditional methods.
3. Using interpretability analysis to obtain clinical insights into feature importance.
4. Exploring real-world applications of machine learning in healthcare to complement traditional diagnostic techniques.

---

## II. Dataset Description

The UCI Heart Disease dataset is widely regarded as a benchmark in the machine learning community. It contains 1,025 samples and 14 features, including continuous and categorical variables. The target variable is binary, indicating the presence (1) or absence (0) of heart disease.

### Dataset Features
- **age**: Age in years.
- **gender**: Gender (1 = male, 0 = female).
- **cp**: Chest pain type:
  - 0: Typical angina
  - 1: Atypical angina
  - 2: Non-anginal pain
  - 3: Asymptomatic
- **trestbps**: Resting blood pressure (mm Hg).
- **chol**: Serum cholesterol (mg/dL).
- **fbs**: Fasting blood sugar (>120 mg/dL: 1, otherwise: 0).
- **restecg**: Resting electrocardiographic results:
  - 0: Normal
  - 1: ST-T wave abnormality
  - 2: Left ventricular hypertrophy
- **thalach**: Maximum heart rate achieved.
- **exang**: Exercise-induced angina (1 = yes, 0 = no).
- **oldpeak**: ST depression induced by exercise.
- **slope**: Slope of the peak exercise ST segment:
  - 0: Upsloping
  - 1: Flat
  - 2: Downsloping
- **ca**: Number of major vessels (0-3) colored by fluoroscopy.
- **thal**: Thalassemia:
  - 0: Normal
  - 1: Fixed defect
  - 2: Reversible defect
- **target**: Target variable (1 = heart disease, 0 = no heart disease).

The dataset offers a balanced mix of continuous and categorical variables, making it suitable for various machine learning techniques.

---

## III. Data Preprocessing

To ensure data quality, the following preprocessing steps were applied:

### A. Renaming Variables
Categorical variables were renamed for clarity:
- **gender**: {0: Female, 1: Male}
- **cp**: {0: Typical angina, 1: Atypical angina, 2: Non-anginal pain, 3: Asymptomatic}
- **fbs**: {0: <120 mg/dL, 1: >120 mg/dL}
- **restecg**: {0: Normal, 1: ST-T wave abnormality, 2: Left ventricular hypertrophy}

### B. Handling Outliers
Outliers were detected and removed using methods like Isolation Forest and Elliptic Envelope.

### C. Discretization
Continuous variables such as age and cholesterol were discretized using KBinsDiscretizer to handle skewed distributions and enhance interpretability.

---

## IV. Analysis

### A. Univariate Analysis
- **Categorical Observations**:
  - Male observations were twice as frequent as female observations.
  - 50% of the dataset consisted of asymptomatic chest pain.
- **Continuous Observations**:
  - Most variables showed Gaussian-like distributions with some skewness.
  - Outliers were detected in cholesterol levels.

### B. Bivariate Analysis
- **Categorical Data vs Target**:
  - Men were more likely to have heart disease.
  - Exercise-induced angina significantly increased heart disease risk.
- **Continuous Data vs Target**:
  - Increased cholesterol and blood pressure correlated with higher heart disease risk.
  - Older individuals were more likely to have heart disease.

---

## V. Feature Importance

Random Forest and Gradient Boosting were used to identify key features:
- **thalassemia**
- **oldpeak (ST depression)**
- **cp (chest pain type)**
- **exang (exercise-induced angina)**
- **thalach (maximum heart rate)**

---

## VI. Modeling and Evaluation

### A. Models Implemented
- **Gradient Boosting Classifier**
- **Random Forest Classifier**
- **Decision Tree Classifier**
- **Gaussian Naive Bayes**
- **SVM**
- **MLP Classifier**
- **KNN Classifier**

### B. Hyperparameter Tuning
RandomizedSearchCV was used for optimization, and Gradient Boosting Classifier achieved the highest accuracy of 98.13%.

### C. Learning Curves
Tree-based models showed tendencies to overfit, but ensemble models demonstrated better adaptability.

---

## VII. Results

### Hybrid Methods and Accuracy Scores
- **Gradient Boosting + KNN**: 91.76%
- **Gradient Boosting + Decision Tree**: 95.13%
- **Gradient Boosting + SVC**: 95.88%
- **Decision Tree + SVC**: 98.13% (Best)

---

## VIII. Conclusion

Data preprocessing, including handling outliers and discretizing variables, significantly improved model performance. Ensemble models like Gradient Boosting and Decision Tree + SVC outperformed others, demonstrating their potential in heart disease prediction.

---

## Acknowledgment
We thank the Ghulam Ishaq Khan Institute of Science and Technology for its support and resources.

---

## References

[1] World Health Organization. (2021). Cardiovascular diseases (CVDs). Retrieved from https://www.who.int/news-room/fact-sheets/detail/cardiovascular-diseases-(cvds)  
[2] Smith, S. C., et al. (2018). The importance of early detection and prevention of cardiovascular diseases. *Journal of Cardiology and Health*, 45(6), 234-245.  
[3] Dietterich, T. G. (2000). Ensemble Methods in Machine Learning. *Proceedings of the International Workshop on Multiple Classifier Systems*, 1-15.  
[4] Chen, T., & Guestrin, C. (2016). XGBoost: A scalable tree boosting system. *Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*, 785-794.  
[5] Dua, D., & Graff, C. (2019). UCI Machine Learning Repository. University of California, Irvine. Retrieved from http://archive.ics.uci.edu/ml
