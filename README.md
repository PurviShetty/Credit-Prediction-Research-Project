# Credit_Prediction_Research_Project
MSc in Data Analytics Research Project

Methodolgy used :
![image](https://user-images.githubusercontent.com/78203422/146198338-a839212d-ea52-4382-aa53-d748601c7927.png)

The Research methodology followed for the implementation of the project is CRISP-DM. The steps followed are:
1) data collection 2) data cleaning and transformation 3)Hybrid Feature Selection 4)SMOTE oversampling 5)hybrid prediction model

In order to enable the generalization of the proposed approach, we have used three datasets of varying sizes from the credit risk domain.
The first dataset used is the Small Bussiness Loan Approval dataset. Here, We check if the business will default the repayment of the Loan before giving approvals. It is a large dataset with 899164 records and 27 variables. The second dataset selected is the credit card default prediction dataset(Taiwan). Here, we check if the customer will default on next month's payment. It Comprises of 30000 rows and 25 attributes and was obtained from the UCI repository. The third dataset is a small dataset for German credit scoring with only 1000 records and 20 columns and was taken from the UCI repository.

In the next step, we can see the list of the techniques used for data cleaning and transformation of the datasets. First, add and rename column names according to the dataset description. In dataset 3, along with column names, we all had to replace cell values from codes like A11, A12 to numeric based on the descriptions provided. Then we handled all the null values in dataset 1. since the data was skewed, We have used the mode technique. We have removed special characters like the dollar symbol from the data. Derived new columns wherever required. handled categorical variables using one-hot encoding and hashing.

The next step is feature selection. Here we proposed a new approach of combining six feature selection algorithms of diverse benefits using the voting technique. This proposed approach will help us solve the issue of dimensionality and bias that is caused because of the relational nature of the data. The feature selection algorithm used in this approach is feedforward, the weight of evidence, ANOVA, random forest, extra tree classifier, L1-based feature selection. The voting mechanisms are unanimous- selected by all 6, majority - selected by at least 5, hard-voting - selected by at least 4, soft-voting -selected by at least 3, and any_vote - selected by at least one.

The next step is data balancing. When we look at the pie charts for the target columns of all three datasets, we can see that all the three datasets are highly imbalanced and hence, we have used SMOTE oversampling technique to balance the dataset. The reason for using SMOTE is that it duplicates the minority class and hence there is no information loss as in the case of undersampling.

Once, the data is ready, we move to the modeling stage. Here we have combined base classifiers XGBoost, LightGBM, and CatBoost. Then we combine the predictions obtained by the base classifiers and apply the meta learner classifier on these combined predictions. This technique is called the stacked generalization method. We have used the above boosting algorithm in the research project because datasets are large and high-dimensional. So we need algorithms that work well with a large dataset. The above algorithm provides efficient execution time and uses less memory. Also, these algorithms can handle noisy and categorical data, making them a good choice for the credit risk domain.

While modeling we have also taken care of hyper-parameter tuning. Hyper-parameter tuning is performed to get optimal performance from the models. In this research, we have used grid search for hyper-parameter tuning because it uses an exhaustive search method that will find the absolute best way to tune the parameters.

Dataset links: 
https://www.kaggle.com/mirbektoktogaraev/should-this-loan-be-approved-or-denied?select=SBAnational.csv
https://archive.ics.uci.edu/ml/datasets/default%2bof%2bcredit%2bcard%2bclients
https://archive.ics.uci.edu/ml/datasets/statlog+(german+credit+data)
