# Practical Application III: Comparing Classifiers

## 🗃️ Folders \& Files

🔗 Github Repository: https://github.com/sgmlai/berkmlai/tree/main/PA_3



🔗 data: https://github.com/sgmlai/berkmlai/tree/main/PA_3/data



🔗 README.md: https://github.com/sgmlai/berkmlai/blob/main/PA_3/README.md



🔗 Jupyter Notebook PA\_3: https://github.com/sgmlai/berkmlai/blob/main/PA_3/prompt_III.ipynb



Overview: In this practical application, your goal is to compare the performance of the classifiers we encountered in this section, namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. We will utilize a dataset related to marketing bank products over the telephone.

#### Getting Started

Our dataset comes from the UCI Machine Learning repository. The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns. We will make use of the article accompanying the dataset here for more information on the data and features. The dataset is available in the data folder of this repository.

###### The exercise follows structured approach to achieve the desired result.

#### 📊 Data Understanding

The data represents when human agents make phone calls to a list of clients to sell the deposit. Thus, the result is a binary unsuccessful or successful contact.
We have different categories that build the customer profile that can help the model predicting the result.

Customer data - Reveals customer education, job, marital status, loan information(If any)

1 - age (numeric)

2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')

3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)

4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')

5 - default: has credit in default? (categorical: 'no','yes','unknown')

6 - housing: has housing loan? (categorical: 'no','yes','unknown')

7 - loan: has personal loan? (categorical: 'no','yes','unknown')

Current Campaign Last Contacted data - Comm type, month \& day, duration of call(When contacted)

8 - contact: contact communication type (categorical: 'cellular','telephone')

9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')

10 - day\_of\_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')

11 - duration: last contact duration, in seconds (numeric).

Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.

Additional Campaign data - Number of contacts, Days since last contact, Previous attempts, Previous Campain result.

12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)

13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)

14 - previous: number of contacts performed before this campaign and for this client (numeric)

15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')

Social and economic attributes - Employment rate, Consumer price \& confidence index, Interest rate, No of Employees.

16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)

17 - cons.price.idx: consumer price index - monthly indicator (numeric)

18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)

19 - euribor3m: euribor 3 month rate - daily indicator (numeric)

20 - nr.employed: number of employees - quarterly indicator (numeric)

Output variable (desired target):

21 - y - has the client subscribed a term deposit? (binary: 'yes','no')

From basic understanding, We need to examine what type of customers have purchased marketed products so that the predictions can be used for targeted marketing.

#### 🧹 Data Preparation and Cleaning

We do not have any missing data but the data is highly imbalanced. So, we will utilize SMOTE to reduce the imbalance effect in training the model.

From Heatmap, target variable(y) is highly correlated with campaign and socio economic factors.

At the same time, emp.var.rate, nr.employed, euribor3m are highly correlated over 0.9, This means, two of these columns might not add much value in the predictions.

Lets consider euribor3m, which is the interest rate provided by the bank on the deposits.

#### Feature Engineering

age             int64  - Numeric, needs scaling

job             object - Categorical, One Hot encoding

marital         object - Categorical, One Hot encoding

education       object - Categorical, One Hot encoding

default         object - Categorical, One Hot encoding

housing         object - Categorical, One Hot encoding

loan            object - Categorical, One Hot encoding

contact         object - Categorical, Binary encoding

month           object - Categorical, One Hot encoding

day\_of\_week     object - Categorical, One Hot encoding

duration        int64  - Suggested that this metric does not make sense until the customer is connected over call which can lead to wrong predictions. So, drop the column.

campaign        int64  - Numeric, needs scaling

pdays           int64  - Numeric, needs scaling

previous        int64  - Numeric, needs scaling

poutcome        object - Categorical, One Hot encoding

emp.var.rate    float64 - Drop the column as its 97% correlated with euribor3m

cons.price.idx  float64 - Numeric, needs scaling

cons.conf.idx   float64 - Numeric, needs scaling

euribor3m       float64 - Numeric, needs scaling

nr.employed     float64 - Drop the column as its 97% correlated with euribor3m

y               int64 -   Numeric Target Variable - Map 0 as No and 1 as Yes

#### ✂️ Split the data for Model Training and testing

All categorical columns are encoded with OHE and numerical columns are scaled with StandardScaler

Create training and test data splits with 80% training and 20% test sets.

Because the positive outcome of target variable is only 11.8%, We will use SMOTE to add more data to training dataset and use that enlarged dataset to train the models.

#### 📝 Baseline Model

Create simple baseline model which is DecisionTree with all default parameters and record the evaluation metrics

#### 📏 Simple Logistic Regression Model

Create simple Logistic Regression model with all default parameters and record the evaluation metrics

#### 🔍 Next steps - Compare with other models

Compare Logistic Regression Model with KNeighbors, SVM \& Decision Tree models and record the accuracy score on training and test datasets

Observation: The best Model is SVC with below training.

Training Model:SVM - SVC()

Parameters:{'kernel': \['linear', 'rbf'], 'C': \[0.1, 1, 10]}

Best Parameters for SVM: {'C': 10, 'kernel': 'rbf'}

SVC model is taking too much time for fitting and predictions. So, this may not be right choice for larger datasets

#### 🎯 Tuning the model

We noticed sigmoid and rbf kernels are taking long time for model training. So, we used SVC with linear Kernel and tuned penalty and Learning rate parameters.

We resolved the model training time with this approach but came with trade off on slight decrease in score and test accuracy compared to rbf kernel.

#### 🏆 Findings and Conclusion

#### KNN has best Training Accuracy \& Score. Rest of the model have very close Training accuracy and scores.

#### LinearSVC has the best Test accuracy score with lower training time.

### LinearSVC will be good fit for this dataset

