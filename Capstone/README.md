# 🎓 Predict Student Performance Using Machine Learning

## ❓ Problem Statement:

Predict student performance based on attendance, academic, resources, study time and social factors, using machine learning and provide actionable insights to Schools, teachers and policy makers to plan and design their programs to boost student performance through guidance and mentoring which can result in better academic outcomes.



\*\*Author:\*\* \*Satya G\*  



\## 🧾 Executive Summary



This project leverages data analytics and machine learning techniques to \*\*predict student academic performance\*\* based on demographic, social, and academic factors.  

By analyzing historical data, the study identifies \*\*key factors influencing student outcomes\*\* and provides \*\*actionable insights\*\* for educators and policymakers to improve learning strategies, guidance programs, and overall academic achievement.



---



\## 🎯 Rationale



Understanding the factors that influence student performance is essential for improving education systems.  

By accurately predicting academic outcomes, schools can:

\- Identify \*\*at-risk students\*\* early,  

\- Design \*\*targeted interventions\*\*, and  

\- Optimize \*\*mentorship and guidance programs\*\*.  



This proactive approach enhances student engagement, supports equity, and drives better academic results.



---



\## ❓ Research Question



> How can machine learning models predict student academic performance, and which factors most strongly influence the likelihood of high or low achievement?



---



## \## 📊 Data Sources

The dataset is downloaded from Kaggle in CSV format and included as part of documentation. Careful consideration is given to selecting a dataset that encompasses key factors influencing performance through grades. While visualization and correlation analysis highlight major contributors to predictive outcomes, it is important to recognize that other features can indirectly impact these primary contributors.



\##⚙️ Methodology



## 🧑‍💻 Data Preprocessing and Preparation:

Training a machine learning model needs data to be cleaned, transformed, and structured for better accuracy.
This step involves handling missing values, encoding categorical variables, scaling numerical features, and selecting relevant features.
Proper preprocessing ensures the dataset is optimized for model training, improving performance and reducing bias.

•	Handled missing data using Mode based imputation

•	Encoded the categorical features using Ordinal Encoder and One Hot Encoder.

•	Numerical data is scaled using Standard Scaler.

•	The data is split into train and test sets with 80% training size and 20% test size.



🎯 Model Outcomes or Predictions:

•	This project uses Machine Learning techniques to analyze student performance based on various features like attendance, study habits, prior grades, and socio-economic factors.

•	The model predicts the future grade of the students and provides opportunities for parents, policy makers, teachers \& tutors to proactively involve and contribute to the student’s success.



## 🧮 Modeling

The problem is classification problem as we predict the student grade based on available features. Also, we have multiple classes for prediction. We have considered the following models to solve this problem.

a.	Decision Trees

b.	KNN

c.	Random Forests

d.	SVM

e.	XGBoost

f.	Logistic Regression

We then perform GridSearchCV to perform cross validation and hyper parameter tuning to get better evaluation metrics so that the model performs well for unseen data.

## 📊 Model Evaluation

Based on the above training, testing, validation and tuning of the models, we consider the below evaluation metrics to pick best model for our problem.

Evaluation metrics for this classification:
a.	Accuracy – How well the model predicts the student grade.

b.	Precision - How well the model predicts the higher-grade students.

c.	Recall – How well the model predicts the lower grade students.

d.	F1 score – How well the model classifies both higher and lower grade students.

e.	Confusion matrix – Matrix that show case actual and misclassified predictions.



## 📝 Model Interpretation

1. Attendance and Hours studied have greater influence on Student grade prediction.
2. The color pattern of Attendance, Hours studied, Previous score depicts the clear relationship between the feature value and its impact on grades.
3. Grade 1 SHAP plot has scattered color patters on both sides which means, non-linear effects on predictions. Even the confusion matrix of XGBoost has wrong predictions as Grade 0 and Grade 2

## 💡 Insights

#### •	Takeaways

1. Attendance at school and study hours are significant factors in achieving good grades.
2. Access to appropriate resources is important for academic success.
3. Positive peer influence, parental involvement, and educational background have a beneficial effect on student performance.
4. There are several indirect factors that can contribute to a student's personal growth, such as physical activity and motivation levels.

#### •	Recommendations

##### Schools:

1. Encourage students to maintain consistent attendance.
2. Design awareness programs to increase study hours outside of school.
3. Facilitate student participation in physical and extracurricular activities for personal development.

##### Policy makers:

1. Provide necessary resources for all students to enhance their studies.
2. Develop assistance and relief programs to offer internet services to students from low-income families.

##### Teachers \& Educators:

1. Identify students with declining grade predictions compared to previous scores and schedule interactive sessions.
2. Proactively engage with students and provide guidance to improve their motivation for academic success.

#### •	Future Scope

1. Information related to social interactions can yield deeper insights.
2. Features reflecting student interests can enhance understanding and guide them in specific areas.
3. Plans for college education and career interests can facilitate mentorship and guidance accordingly. 



\## 📈 Results



The model with the best accuracy, F1 score, and recall will be selected for these predictions. It is essential to predict student grades accurately and address the performance of lower-performing students without negatively impacting the grades of high-performing students.

1. False Positive: Students with higher grades are classified into lower grades, which is okay as they can receive guidance. False Negative: Students with lower grades are classified into higher grades, which is NOT okay as they miss the guidance needed for better academic scores.

2.We need to rank our models based on evaluation metric which minimizes False Negatives and also have balance with False Negatives and Positives.

3.XGBoost seems to be the best model for this classification problem.

4.XGBoost has better Recall and F1 Score on test set.

5.Moreover, from confusion matrices, lower grade students are less classified into higher grades with XGBoost when compared with SVM.



---



\## 🚀 Next Steps



\- Integrate \*\*real-time school data\*\* for continuous prediction.  

\- Develop a \*\*dashboard\*\* for teachers to identify at-risk students.  

\- Expand to datasets from different regions and education levels.  

\- Collaborate with schools to embed \*\*predictive analytics\*\* into mentoring and support programs.



---





🗃️ Folders \& Files

🔗 Github Repository: https://github.com/sgmlai/berkmlai/tree/main/Capstone

🔗 data: https://github.com/sgmlai/berkmlai/tree/main/Capstone/data

🔗 README.md: https://github.com/sgmlai/berkmlai/blob/main/Capstone/README.md

🔗 Jupyter Notebook PA_3: https://github.com/sgmlai/berkmlai/blob/main/Capstone/Predict_Student_Performance.ipynb

This Jupyter Notebook contains the libraries and code for exploratory analysis, Feature Engineering, Modeling, Model Evaluation metrics and Results.

🔗 Capstone Project\_Final.docx: https://github.com/sgmlai/berkmlai/blob/main/Capstone/Capstone_Project_Final.docx

Word document that reports detail about project along with results of analysis



