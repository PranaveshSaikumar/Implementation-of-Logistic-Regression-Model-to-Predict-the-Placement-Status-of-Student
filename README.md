# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
<br><br>
## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook
<br><br>
## Algorithm
step 1. Import the Standard Libraries 

step 2. Set Variables for Assigning Dataset Values

step 3. Import Logistic Regression from sklearn

step 4. Assign the Points for Representing in the Graph 

step 5. Predict the Placement Status by Using the Logistic Regression Model

step 6. Compare the Graphs and Evaluate the Model's Performance
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
## Program:
```
/*Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Pranavesh Saikumar*/

RegisterNumber: 212223040149 
import pandas as pd
data = pd.read_csv("C:/Users/admin/OneDrive/Desktop/Placement_Data.csv")
print(data.head())
data1= data.copy()
data1= data1.drop(["sl_no","salary"],axis=1)
data1.head()
data1.isnull()
from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data1["gender"]= le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]= le.fit_transform(data1["hsc_b"])
data1["hsc_s"]= le.fit_transform(data1["hsc_s"])
data1["degree_t"]= le.fit_transform(data["degree_t"])
data1["workex"]= le.fit_transform(data1["workex"])
data1["specialisation"]= le.fit_transform(data1["specialisation"])
data1["status"]= le.fit_transform(data1["status"])
data1
x= data1.iloc[:,:-1]
x
y=data1["status"]
y
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test= train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.linear_model import LogisticRegression
lr= LogisticRegression(solver="liblinear")
lr.fit(x_train,y_train)
y_pred= lr.predict(x_test)
y_pred
from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)
accuracy
from sklearn.metrics import classification_report
classification_report1= classification_report(y_test,y_pred)
print(classification_report1)
lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])
```

## Output:
![Screenshot 2024-09-16 102823](https://github.com/user-attachments/assets/dbcdd5fb-bccf-43c7-a7f3-1f8b3715e341)

Classification Report:

![Screenshot 2024-09-16 102829](https://github.com/user-attachments/assets/cf3d9c79-fd9d-4ea5-9951-6e309cc63ad8)

## Result:

Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
