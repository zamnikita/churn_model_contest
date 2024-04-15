# churn_model_contest
Solving for the [churn prediction problem](https://ods.ai/competitions/data-fusion2024-churn) in Data Fusion Contest 2024.

# Data
Can be found at the [link](https://ods.ai/competitions/data-fusion2024-churn/dataset).

# Libraries

pandas, sklearn, sksurv, xgboost, matplotlib

# Solutions

## baseline_elastic_net_cox_model.ipynb

Pipeline consists of [StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html) (from sklearn.preprocessing) and [CoxnetSurvivalAnalysis](https://scikit-survival.readthedocs.io/en/stable/api/generated/sksurv.linear_model.CoxnetSurvivalAnalysis.html) (from sksurv.linear_model).

Metric is [concordance index](https://lifelines.readthedocs.io/en/latest/lifelines.utils.html).

Test concordance index=0.7094, train concordance index=0.7184.


## baseline_xgboost.ipynb

More features were extracted from the transactions history. 

### Linear model
The categorical features were encoded using [OneHotEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html) (from sklearn.preprocessing) for the Cox proportional hazards model.

Test concordance index=0.7378, train concordance index=0.7528.

### XGBoost model

The [Accelerated Failure Time model](https://xgboost.readthedocs.io/en/stable/tutorials/aft_survival_analysis.html#accelerated-failure-time-model) was built with XGBoost. The categorical features were processed with the [XGBoost model](https://xgboost.readthedocs.io/en/stable/tutorials/categorical.html). The hyperparameters were tuned with the [Optuna](https://optuna.readthedocs.io/en/v2.0.0/index.html).

Test Concordance index=0.7510

Valid Concordance index=0.7565

Train Concordance index=0.8077