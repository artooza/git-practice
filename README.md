# Bank Marketing Prediction

An **end-to-end machine learning project** to predict whether a customer will subscribe to a bank term deposit using customer characteristics, campaign information, and macroeconomic indicators.

The project demonstrates a complete data science workflow, including exploratory data analysis, feature engineering, model development, hyperparameter tuning, model interpretation, and business recommendations.


## Business Problem

A Portuguese bank conducts direct marketing campaigns through phone calls to promote term deposit products. Each contact has operational costs, while only a small percentage of customers subscribe.

The objective of this project is to build a predictive system that identifies customers with a higher probability of subscription before launching a campaign.

This approach can help the bank:

- Increase campaign conversion rates
- Reduce unnecessary customer contacts
- Improve marketing resource allocation
- Support data-driven decision-making


## Project Workflow

The project follows an end-to-end machine learning pipeline:

1. Data Cleaning
2. Exploratory Data Analysis (EDA)
3. Feature Engineering
4. Feature Selection Analysis
5. Data Preprocessing
6. Model Development
7. Hyperparameter Optimization
8. Model Evaluation
9. Model Interpretation
10. Business Recommendations


## Dataset

The dataset used in this project is the **Bank Marketing Dataset** from the UCI Machine Learning Repository.

It contains:

- Customer demographic information
- Previous campaign interactions
- Marketing campaign characteristics
- Macroeconomic indicators
- Subscription outcome

Target variable(y):


- **yes** → Customer subscribed to term deposit
- **no** → Customer did not subscribe


## Repository Structure

```text
bank-marketing-prediction
│
├── notebooks
│   ├── EDA_and_Preprocessing.ipynb
│   └── Model_Training_and_Evaluation.ipynb
│
├── README.md
└── requirements.txt
```


## Machine Learning Models

**The following classification algorithms were evaluated:**

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- LightGBM
- CatBoost

**Hyperparameter optimization was performed using:**

- GridSearchCV
- Stratified K-Fold Cross Validation


## Model Evaluation

Models were compared using multiple evaluation metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC

Example evaluation table:

| Model | F1-score | ROC-AUC | PR-AUC | Selected |
|------|---------:|--------:|-------:|:--------:|
| Random Forest | 0.509 | 0.812 | 0.482 | Yes |
| Random Forest (Tuned) | 0.498 | 0.811 | 0.481 | |
| XGBoost | 0.486 | 0.798 | 0.462 | |
| CatBoost (Tuned) | 0.485 | 0.812 | 0.480 | |
| LightGBM | 0.485 | 0.800 | 0.471 | |
| CatBoost | 0.484 | 0.808 | 0.482 | |
| Decision Tree | 0.470 | 0.793 | 0.453 | |
| Logistic Regression | 0.463 | 0.802 | 0.448 | |

## Final Model Selection

Random Forest achieved the best overall predictive performance, obtaining the highest F1-score (0.509) and ROC-AUC (0.812) while maintaining good generalization between training and test datasets.

Therefore, Random Forest was selected as the final model for interpretation and business recommendations.


## Model Interpretation

To understand why the model makes predictions, multiple explainability techniques were applied:

- Built-in Feature Importance
- Permutation Importance
- SHAP Analysis
- Logistic Regression Coefficient Analysis

These methods provide insight into the main factors influencing customer subscription decisions.


## Key Business Insights

- Previous customer interactions were the strongest predictors of subscription probability, indicating that historical campaign success is highly valuable for customer targeting.

- Macroeconomic indicators such as euribor3m, emp.var.rate, and nr.employed significantly influenced customer decisions.

- Campaign strategy variables showed that excessive contact attempts may reduce conversion probability.

- Behavioral features provided more predictive power than demographic characteristics.

- Model interpretation using SHAP, Feature Importance, and Permutation Importance increased confidence in the identified drivers.

- Predictive targeting can help reduce marketing costs and improve campaign efficiency.


## Limitations

This project has several limitations:

- The dataset represents a single Portuguese bank and may not fully generalize to other institutions.
- Customer behavior can change over time, requiring model updates.
- Additional customer information such as transaction history was unavailable.
- The dataset contains class imbalance, which may influence model behavior.
- Economic variables contain multicollinearity, requiring careful interpretation.


## Conclusion

This project developed a machine learning system to predict customer subscription to bank term deposits.

Multiple classification models were compared, and Random Forest was selected as the final model based on predictive performance and generalization ability.

Model interpretation techniques showed that previous customer interactions, campaign characteristics, and macroeconomic conditions were the most influential factors affecting subscription decisions.

The results demonstrate that combining predictive modeling with explainability can provide both accurate predictions and actionable business insights for improving marketing strategies.


## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- LightGBM
- CatBoost
- SHAP
- Jupyter Notebook


### Author

**Atefeh Mina**

Data Science | Machine Learning | Financial Analytics
