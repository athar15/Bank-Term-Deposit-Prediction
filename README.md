# 📊 Bank Term Deposit Prediction

## About the Project

Banks often run marketing campaigns to encourage customers to open term deposits. Reaching every customer, however, is both time-consuming and costly. The goal of this project is to analyse customer data and build a machine learning model that can predict which customers are more likely to subscribe to a term deposit.

The project is divided into two parts:

* **Exploratory Data Analysis (EDA)** to understand customer behaviour and identify important patterns.
* **Machine Learning** to build and compare different classification models.

---

## Project Objectives

* Explore customer and campaign data to identify meaningful insights.
* Understand the factors that influence term deposit subscriptions.
* Build multiple machine learning models for prediction.
* Compare model performance and select the best model for the business problem.

---

## Dataset

This project uses the **Bank Marketing Dataset** from the UCI Machine Learning Repository.

**Dataset Summary**

* **Rows:** 41,188
* **Features:** 20 input features and 1 target variable
* **Target Variable:** `subscribe`

  * **Yes** – Customer subscribed
  * **No** – Customer did not subscribe

---

## Tools & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* SVM
* Jupyter Notebook

---

## Exploratory Data Analysis

During the analysis, I explored customer demographics, previous campaign information and economic indicators to understand their relationship with term deposit subscriptions.

The following analyses were performed:

* Data inspection
* Missing value analysis
* Duplicate value analysis
* Target variable analysis
* Numerical feature analysis
* Categorical feature analysis
* Correlation analysis
* Business insight generation
* Data visualization

### Key Insights

* The dataset is highly imbalanced, with approximately **89% "No"** and **11% "Yes"** responses.
* Customers between **30–50 years** represent the largest customer segment.
* **Students** and **retired customers** have the highest subscription rates.
* Customers contacted through **cellular phones** are more likely to subscribe than those contacted via telephone.
* Customers with a **successful previous marketing campaign** have a significantly higher probability of subscribing again.
* Strong correlations exist among several economic indicators, indicating possible multicollinearity.

---

## Machine Learning Workflow


## Data Preprocessing

The following preprocessing steps were performed before model training:

* Removed the **duration** feature to prevent data leakage.
* Encoded the target variable (`Yes = 1`, `No = 0`).
* Applied stratified train-test split.
* Imputed numerical features using the median.
* Imputed categorical features using the most frequent value.
* Standardized numerical features using StandardScaler.
* Applied One-Hot Encoding to categorical variables.
* Built a preprocessing pipeline using Scikit-learn.
  
---

## Machine Learning Models

The following classification models were trained and evaluated:

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier
* Support Vector Machine (SVM)
* XGBoost Classifier

---

## Model Performance

| Model                  | Accuracy | Precision |     Recall |   F1 Score |
| ---------------------- | -------: | --------: | ---------: | ---------: |
| Support Vector Machine |   85.21% |    39.69% |     58.29% | **47.23%** |
| Logistic Regression    |   82.70% |    34.93% | **60.75%** |     44.36% |
| XGBoost                |   89.49% |    57.32% |     28.88% |     38.41% |
| Random Forest          |   89.06% |    53.48% |     27.91% |     36.68% |
| Decision Tree          |   83.55% |    28.92% |     30.80% |     29.83% |

Although XGBoost and Random Forest achieved higher accuracy, the dataset is imbalanced, so **F1 Score** and **Recall** were considered more important than accuracy. Based on these metrics, **Support Vector Machine (SVM)** performed the best and was selected as the final model because it achieved the highest **F1 Score (47.23%)** while maintaining a good balance between Precision and Recall.

---

## Hyperparameter Tuning

To improve the performance of the selected model, **GridSearchCV** was implemented for hyperparameter tuning of the Support Vector Machine (SVM).

The tuning process was configured using **5-fold cross-validation** to evaluate different combinations of hyperparameters, including:

* **C:** `[0.1, 1, 10]`
* **Kernel:** `['linear', 'rbf']`
* **Gamma:** `['scale', 'auto']`

This resulted in **12 hyperparameter combinations** evaluated across **5 folds**, requiring a total of **60 model fits**.

Due to the computational time required for training on the full dataset, the tuning process was initiated but the final optimized parameters were not available at the time this project was documented. Therefore, the model comparison and conclusions presented in this repository are based on the original model configurations.

--------

## Key Takeaways

* Previous campaign outcomes strongly influence future subscription behaviour.
* Cellular communication proved more effective than telephone calls.
* Students and retired customers represent valuable target segments.
* A balanced evaluation metric such as F1 Score provides a better assessment than accuracy for imbalanced datasets.

---

## Business Recommendations

* Prioritize marketing campaigns for **students** and **retired customers**, as they showed the highest subscription rates.
* Prefer **cellular communication** over telephone calls to improve campaign effectiveness.
* Target customers who responded successfully in previous campaigns, as they have a higher likelihood of subscribing again.
* Focus marketing efforts on customer segments with higher conversion potential instead of contacting all customers.
* Use the trained SVM model to identify potential subscribers before launching marketing campaigns, helping reduce marketing costs and improve conversion rates.

-----

## Repository Structure

```text
Bank-Term-Deposit-Prediction/
│
├── 01_Bank_Marketing_EDA.ipynb
├── 02_Bank_Term_Deposit_Prediction.ipynb
├── README.md
```

---

Md Athar Imam







tps://github.com/YOUR_GITHUB
