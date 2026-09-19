# Customer_Churn_Prediction_Analytics
Customer churn prediction using transactional data, feature engineering, Databricks, and machine learning.

📌 **Project Overview**

This project analyses customer purchasing behaviour for FoodCorp to understand customer engagement and identify patterns associated with customer churn.

Using transaction data from 22 July 2020 to 22 March 2022, covering 9,288 customers and 19,823 products, the project applies data analytics and machine learning to examine customer behaviour and predict potential churn.

The analysis compares the behaviour of churned and non-churned customers and identifies key behavioural patterns that can support more targeted customer retention activities.

🎯 **Business Problem**

Customer churn is an important challenge for FoodCorp, as changes in purchasing activity can indicate that customers are becoming less engaged.

The project aims to use historical transaction behaviour to identify customers at risk of churn and understand the behavioural patterns associated with customer inactivity.

The analysis focuses on understanding changes in:

* Customer visits
* Spending behaviour
* Product purchasing patterns
* Overall customer engagement

The resulting insights and predictive modelling provide a data-driven basis for understanding customer churn and supporting targeted retention initiatives.

📊**Dataset**

The project uses FoodCorp transactional data covering the period from 22 July 2020 to 22 March 2022. The dataset contains transaction records covering 9,288 unique customers and 19,823 distinct products, providing the basis for analysing purchasing behaviour, customer engagement and churn.

The data was used to develop customer-level behavioural features, including purchasing frequency, spending, product diversity and recency, which were subsequently used in the churn analysis and machine learning models.

🔐 **Dataset Accessibility**

Note: The underlying transactional dataset is not included in this repository due to data accessibility restrictions. The repository therefore focuses on the analytical code, methodology, and project findings.

🛠️ **Tools & Technologies**

Python | SQL | Databricks | Pandas | Scikit-learn | LightGBM | Temporal Analysis | Machine Learning | Feature Engineering

🔬 **Methodology**

The project follows an end-to-end temporal customer churn prediction workflow, combining transactional analysis, feature engineering and machine learning.

1. Data Validation & Preparation
    Transaction data was checked for data quality, including customer, product, receipt and transaction-date information.
2. Churn Labelling
    Customers were classified as churned when they had more than 42 consecutive days without a purchase.
3. Feature Engineering
    SQL was used to create features capturing recent and historical customer behaviour, including:
    * Store visits and total spend
    * Purchase recency
    * Unique products and stores
    * Lagged visits and spending
    * Behaviour across 1-week, 4-week and 7-week periods
4. Feature Analysis
    Feature relationships were analysed to identify highly correlated and overlapping variables before modelling.
5. Temporal Data Splitting
    Data was divided chronologically into training, validation and test periods. This ensured that future information was not used during model development and reduced the risk of data leakage.
6. Model Development & Selection
    Three classification models were evaluated:
    * Logistic Regression
    * LightGBM
    * Random Forest
    Random Forest was selected based on its stronger validation performance, achieving 89% accuracy, 87% precision and 99% recall, with the highest F1-score and ROC-AUC among the evaluated models.
7. Hyperparameter Tuning
    GridSearchCV with temporal cross-validation was used to optimise the Random Forest model. The primary tuning metric was ROC-AUC.
8. Final Evaluation & Feature Importance
    The selected model was retrained using the combined training and validation data and assessed on the holdout test period. Model performance was evaluated using Accuracy, Precision, Recall, F1-score and ROC-AUC. Permutation importance was then used to examine the contribution of features to the model’s predictions.

👥 **Key Customer Insights**

The analysis identified clear differences in purchasing behaviour between churned and non-churned customers:

* Product diversity: Non-churned customers purchased approximately three times more unique products than churned customers.
* Visit frequency: Retained customers visited more than twice as frequently in the previous month compared with churned customers.
* Declining engagement: Churned customers showed noticeable reductions in shopping visits and spending in the weeks before becoming inactive.
* Customer purchasing patterns: Churned customers showed a sharp reduction in visits, spending and product range, while loyal customers generally maintained more regular and broader purchasing behaviour.
* Category preferences: Fruit and Cigarettes were popular across both groups, while Salad and Deli were highlighted among churned customers and Paypoint and Milk among non-churned customers.

## 📊 Visual Results

The project report contains the key visualisations used throughout the analysis, including customer churn distribution, customer behavioural patterns, product diversity and feature importance.

**[View Full Project Report](Business_report.docx)**

📄 **Project Documentation**

For a detailed explanation of the project, including the business problem, methodology, feature engineering, model development, evaluation and results, see the full project report:

**[View Full Project Report](Business_report.docx)**

💻 **Code & Analysis Notebook**

The project analysis was developed in **Databricks**, combining **SQL and Python** for data preparation, feature engineering, exploratory analysis and machine learning.

The notebook covers:

- Transaction data preparation and validation

- Customer-level feature engineering using SQL

- Customer behavioural analysis

- Churn labelling based on the 42-day inactivity definition

- Temporal training, validation and test data splitting

- Development and comparison of Logistic Regression, LightGBM and Random Forest models

- Hyperparameter tuning using GridSearchCV and temporal cross-validation

- Model evaluation using Accuracy, Precision, Recall, F1-score and ROC-AUC

- Permutation-based feature importance analysis


The extracted notebook cells are also provided for easier inspection of the underlying SQL and Python code:

**[View Databricks Analysis Notebook](Churn_Prediction_Code.ipynb)**

