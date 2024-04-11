# churn_model_contest
Solving for the [churn prediction problem](https://ods.ai/competitions/data-fusion2024-churn) in Data Fusion Contest 2024.

# Data
Can be found at the [link](https://ods.ai/competitions/data-fusion2024-churn/dataset).

# Solutions

## baseline_elastic_net_cox_model.ipynb

Pipeline consists of StandardScaler (from sklearn.preprocessing) and CoxnetSurvivalAnalysis (from sksurv.linear_model).

Metric is [concordance index](https://lifelines.readthedocs.io/en/latest/lifelines.utils.html).

Test concordance index=0.7094, train concordance index=0.7184.
