# 💰 Finding Donors for CharityML (Supervised Learning)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange)
![Machine Learning](https://img.shields.io/badge/ML-Supervised%20Learning-green)

## 📌 Project Overview
CharityML is a non-profit organization that seeks to identify potential donors to maximize the impact of their fundraising campaigns. Since the cost of outreach is high, the goal is to predict which individuals earn more than **$50,000** annually, as they are statistically more likely to donate.

This project involves building a classification model using the 1994 U.S. Census data to accurately target high-income individuals.

---

## 📊 Dataset Statistics
The dataset provides a comprehensive look at demographic factors influencing income:
* **Total Records:** 45,222 data points.
* **Input Features:** 13 (Age, Education, Occupation, Marital Status, etc.).
* **Target Variable:** `income` (Classified as >50K or <=50K).
* **Class Imbalance:** Roughly 24.78% of individuals earn >50K, while 75.22% earn <=50K. 

---

## 🛠 Feature Engineering & Preprocessing
To ensure model stability and performance, I implemented a rigorous preprocessing pipeline:
* **Log Transformation:** Applied $log(x + 1)$ to skewed features (`capital-gain` and `capital-loss`) to normalize the distribution and minimize the impact of outliers.
* **Feature Scaling:** Used `MinMaxScaler` to normalize numerical features into the range [0, 1], preventing features with larger magnitudes from dominating the learning process.
* **One-Hot Encoding:** Converted categorical variables into 103 binary features using `pd.get_dummies()` for mathematical compatibility with the algorithms.

---

## 🔬 Model Selection & Evaluation
I evaluated three supervised learning models to find the most cost-effective predictor:
1. **Logistic Regression** (Baseline).
2. **Support Vector Machines (SVM)**.
3. **AdaBoost Classifier** (Selected as the Final Model).

### Evaluation Metric: F-beta Score ($\beta = 0.5$)
Since CharityML has a limited budget, we prioritized **Precision** over Recall. 
* **Reasoning:** It is more important to avoid "False Positives" (sending mail to someone who won't donate) than to find every single potential donor. The F-beta score allows us to weigh Precision more heavily.

---

## 📈 Final Model Results
After fine-tuning the **AdaBoost** model using **GridSearchCV**, the model achieved:
- **Accuracy Score:** [87.0%]
- **F-Score:** [90.35%]

### Key Feature Insights
The model identified the top 5 features influencing high income:
1. **Capital-gain** (Most significant indicator).
2. **Education-num** (Years of education).
3. **Age**.
4. **Hours-per-week**.
5. **Marital Status**.



---

## 🚀 Installation & Setup
**Clone the Repository**
   ```bash
   git clone [https://github.com/markwael/CharityML-Finding-Donors.git] (https://github.com/markwael/CharityML-Finding-Donors.git)
1. **Clone the repo:**
   ```bash
   git clone [https://github.com/markwael/CharityML-Finding-Donors.git](https://github.com/markwael/CharityML-Finding-Donors.git)
