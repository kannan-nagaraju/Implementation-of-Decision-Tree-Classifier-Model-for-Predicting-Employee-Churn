# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
#### 1.import pandas module and import the required data set.
#### 2.Find the null values and count them.
#### 3.Count number of left values.
#### 4.From sklearn import LabelEncoder to convert string values to numerical values.
#### 5.From sklearn.model_selection import train_test_split.
#### 6.Assign the train dataset and test dataset.
#### 7.From sklearn.tree import DecisionTreeClassifier.
#### 8.Use criteria as entropy.
#### 9.From sklearn import metrics.
#### 10.Find the accuracy of our model and predict the require values.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: KANNAN N
RegisterNumber:212223230097
*/
```
```
import pandas as pd
data = pd.read_csv("Employee.csv")
data
data.head()
data.info()
data.isnull().sum()
data["left"].value_counts
from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)
from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:
## Data
![image](https://github.com/user-attachments/assets/60d4ddaf-2a1f-451f-a17c-521a34a84f1c)

## Accuracy
![image](https://github.com/user-attachments/assets/c9b9ff8e-fb04-4ce4-8250-93cf416ee072)

## Predict
![image](https://github.com/user-attachments/assets/0fdd4f93-0ccc-4932-948e-ba4a6f4f65cc)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
