# Bank Marketing Prediction
## Project Overview
This project develops a machine learning model to predict whether a customer will subscribe to a term deposit offered through a Portuguese bank's telemarketing campaign. The project follows a complete end-to-end data science workflow, including data cleaning, exploratory data analysis (EDA), feature engineering, model development, hyperparameter tuning, model interpretation, and business recommendations.
The objective is not only to build an accurate predictive model but also to generate actionable business insights that can improve marketing efficiency and decision-making.

## Business Problem
A Portuguese bank conducts direct marketing campaigns through phone calls to promote term deposit products. Every phone call incurs operational costs, including agent time and telecommunication expenses, while excessive contact may negatively affect customer satisfaction.
Since only a small proportion of contacted customers subscribe to the product, the bank needs a predictive system to identify customers who are most likely to purchase the product before initiating a call.
Such a system helps the bank:
- Increase campaign conversion rates
- Reduce operational costs
- Improve customer experience by minimizing unnecessary calls
- Allocate marketing resources more efficiently

## Business Objectives
The primary objective of this project is to develop a predictive model that supports more effective and data-driven bank marketing campaigns.

**The specific objectives are:**
- Predict customer subscription before campaign execution.
- Identify high-potential customers for targeted marketing.
- Reduce unnecessary marketing costs and improve campaign efficiency.
- Compare multiple machine learning models and select the best-performing one.
- Interpret the final model to identify the key drivers of customer subscription.

## Dataset
The dataset is the Bank Marketing Dataset from the 
[UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/222/bank+marketing).
It contains demographic information, previous marketing interactions, economic indicators, and campaign-related attributes collected during direct marketing campaigns conducted by a Portuguese bank.

## Project Workflow
The project follows a standard industrial data science pipeline:
1.	Data Cleaning
2.	Exploratory Data Analysis (EDA)
3.	Feature Engineering
4.	Feature Selection Analysis
5.	Model Development
6.	Hyperparameter Optimization
7.	Model Evaluation
8.	Model Interpretation
9.	Business Insights and Recommendations

## Machine Learning Models
**Models evaluated:**
- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost / LightGBM / CatBoost

**Hyperparameter tuning:**
- GridSearchCV
- Stratified K-Fold Cross Validation

## Business Insights
The findings of this study provide several actionable insights that can improve the effectiveness of future bank marketing campaigns.

**1. Focus on customers with successful previous interactions**
Previous customer interactions emerged as one of the strongest predictors across all analyses. Variables such as poutcome_success and was_contacted_before consistently increased the likelihood of subscription. This suggests that customers who have previously responded positively to marketing campaigns should be prioritized in future campaigns, as they represent high-probability conversion targets.

**2. Macroeconomic conditions play a critical role in campaign success**
Macroeconomic variables, including euribor3m, emp.var.rate, and nr.employed, consistently appeared as the most influential predictors in Feature Importance, Permutation Importance, and SHAP analyses. This indicates that customer decisions are strongly associated with the economic environment rather than solely with individual characteristics.
Although Logistic Regression produced mixed coefficient signs for some macroeconomic variables, these coefficients should be interpreted cautiously due to the multicollinearity identified earlier in the analysis. The consistency between Feature Importance and SHAP provides stronger evidence for their importance.

**3. Campaign design influences customer response**
Campaign-related variables such as campaign, contact, and several interaction features involving month_contact consistently appeared among the important predictors.
The SHAP analysis showed that increasing the number of contact attempts generally reduced the probability of subscription, while Logistic Regression also assigned negative coefficients to several campaign-related variables.
However, the effects associated with specific months should not be interpreted as causal because campaign timing is highly correlated with macroeconomic conditions.

**4. Customer behavior is more informative than demographic characteristics**
Behavioral variables, including previous campaign outcomes, previous contacts, and campaign history, consistently demonstrated greater predictive power than demographic variables such as age, education, or occupation.
Although age appeared among the important variables, most demographic features showed relatively low importance in both SHAP and Permutation Importance analyses.

**5. Model explainability increases confidence in business decisions**
Three independent interpretation techniques—Built-in Feature Importance, Permutation Importance, and SHAP—identified largely the same key predictors. Logistic Regression also supported many of these findings despite its linear assumptions.
The consistency across multiple interpretation methods increases confidence that the identified drivers are genuine rather than artifacts of a single model.

**6. Predictive targeting can improve marketing efficiency**
The Random Forest model achieved the strongest overall predictive performance while maintaining good generalization between training and test datasets. It also outperformed the other models in terms of F1-score and ROC-AUC.
Instead of contacting every customer, the bank can rank customers according to predicted subscription probability and allocate marketing resources to those with the highest likelihood of conversion. This approach is expected to reduce marketing costs while improving campaign efficiency and return on investment.

## Limitations
This study has several limitations that should be acknowledged.
- The dataset represents a single banking institution and may not generalize to other financial institutions or countries.
- Customer behavior may evolve over time, requiring periodic model updates.
- Although several feature engineering techniques were applied, additional external information (e.g., customer transaction history or credit scores) was unavailable.
- The dataset is moderately imbalanced, which may still influence model behavior despite using balanced learning techniques.
- Logistic Regression coefficients for macroeconomic variables should be interpreted cautiously because multicollinearity exists among these predictors.

## Conclusion
This study developed and evaluated several machine learning models to predict whether a customer would subscribe to a bank term deposit using the Bank Marketing dataset. A comprehensive data preprocessing pipeline was designed, including hidden missing value handling, feature engineering, outlier treatment, categorical encoding, and feature scaling where appropriate.

Six classification algorithms were compared using multiple evaluation metrics, including Accuracy, Precision, Recall, F1-score, ROC-AUC, and PR-AUC. Although several models achieved competitive predictive performance, Random Forest demonstrated the best overall balance between discrimination ability and classification performance, making it the final model selected for prediction.

To improve model transparency and interpretability, multiple explainability techniques—including Built-in Feature Importance, Permutation Importance, SHAP, and Logistic Regression coefficient analysis—were employed. These complementary analyses consistently identified previous customer interactions, campaign-related variables, and macroeconomic indicators as the primary factors influencing subscription decisions.

The findings suggest that customer behavior is driven more by historical interactions and economic conditions than by demographic characteristics alone. Consequently, data-driven customer targeting has the potential to improve marketing efficiency, reduce unnecessary campaign costs, and increase conversion rates.

Overall, this study demonstrates that combining predictive modeling with model interpretability provides not only accurate predictions but also valuable business insights that can support more informed marketing decisions in the banking sector.
