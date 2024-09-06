# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

Step 1 :
Import the standard libraries such as pandas module to read the corresponding csv file.

Step 2 :
Upload the dataset values and check for any null or duplicated values using .isnull() and .duplicated() function respectively.

Step 3 :
Import LabelEncoder and encode the corresponding dataset values.

Step 4 :
Import LogisticRegression from sklearn and apply the model on the dataset using train and test values of x and y.

Step 5 :
Predict the values of array using the variable y_pred.

Step 6 :
Calculate the accuracy, confusion and the classification report by importing the required modules such as accuracy_score, confusion_matrix and the classification_report from sklearn.metrics module.

Step 7 :
Apply new unknown values and print all the acqirred values for accuracy, confusion and the classification report.

Step 8:
End the program.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by:Sharan G 
RegisterNumber:212223230203  
*/
import pandas as pd
data=pd.read_csv("/content/Placement_Data.csv")
data.head()

data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)
data1.head()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"]=le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]=le.fit_transform(data1["hsc_b"])
data1["hsc_s"]=le.fit_transform(data1["hsc_s"])
data1["degree_t"]=le.fit_transform(data1["degree_t"])
data1["workex"]=le.fit_transform(data1["workex"])
data1["specialisation"]=le.fit_transform(data1["specialisation"])
data1["status"]=le.fit_transform(data1["status"])
data1

data1.isnull()

x=data1.iloc[:,:-1]
x

y=data1["status"]
y

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.linear_model import LogisticRegression
lr=LogisticRegression(solver="liblinear")
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
y_pred

from sklea.metrics import accuracy_scorern
accuracy=accuracy_score(y_test,y_pred)
accuracy

from sklearn.metrics import classification_report
classification_report1=classification_report(y_test,y_pred)
print(classification_report1)


lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])

```


## Output:
![Screenshot 2024-09-06 101533](https://github.com/user-attachments/assets/2e746a95-932a-4982-be76-1c18e0262c03)
![Screenshot 2024-09-06 101539](https://github.com/user-attachments/assets/46abb67a-3a80-44e1-b64f-59fa1547f7ff)
![Screenshot 2024-09-06 101545](https://github.com/user-attachments/assets/d78c32f0-994c-42cb-a463-4b28fffc2ff1)
![Screenshot 2024-09-06 101552](https://github.com/user-attachments/assets/6d4b53dc-efaa-4731-9705-507d3343ef8b)
![Screenshot 2024-09-06 101557](https://github.com/user-attachments/assets/2b69d859-d043-4925-8383-1fc8aa4eeb30)
![Screenshot 2024-09-06 101604](https://github.com/user-attachments/assets/44c2cf8f-ce83-41a8-833c-8427104ef8a1)
![Screenshot 2024-09-06 101614](https://github.com/user-attachments/assets/a9d3ca1e-625b-41eb-8c7e-31d9e7496eea)
![Screenshot 2024-09-06 101614](https://github.com/user-attachments/assets/07d42b6e-5a1b-43c0-8518-193337beba4c)
![Screenshot 2024-09-06 101632](https://github.com/user-attachments/assets/8460f82e-1247-427c-b288-ddeb41afd01b)

## Result:

Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
