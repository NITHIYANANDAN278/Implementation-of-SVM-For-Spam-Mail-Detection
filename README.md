# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.import the required packages.
2.Import the dataset to operate on.
3.Split the dataset.
4.Predict the required output.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: NITHIYANANDAN N
RegisterNumber:212222230099
*/
import chardet
file='/content/spam.csv'
with open(file,'rb') as rawdata:
  result = chardet.detect(rawdata.read(100000))
result


import pandas as pd
data=pd.read_csv('/content/spam.csv',encoding='Windows-1252')

data.head()

data.info()

data.isnull().sum()

x=data["v1"].values
y=data["v2"].values

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()

x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)

from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## Output:
### Data head()
![image](https://github.com/NITHIYANANDAN278/Implementation-of-SVM-For-Spam-Mail-Detection/assets/121784636/50c4a448-5229-4b86-9846-01878cd83dca)
### Data info()
![image](https://github.com/NITHIYANANDAN278/Implementation-of-SVM-For-Spam-Mail-Detection/assets/121784636/85302d07-1485-49ba-a8b1-32e8669a2fac)
### Data.isnull().sum()
![image](https://github.com/NITHIYANANDAN278/Implementation-of-SVM-For-Spam-Mail-Detection/assets/121784636/6945795f-d246-4d64-bb60-5825e0e1be9d)
### y_pred
![image](https://github.com/NITHIYANANDAN278/Implementation-of-SVM-For-Spam-Mail-Detection/assets/121784636/af9d25b7-3792-499e-ae53-bbd7d74df5cb)
### Accuracy
![image](https://github.com/NITHIYANANDAN278/Implementation-of-SVM-For-Spam-Mail-Detection/assets/121784636/cf18d205-f3bb-4a19-b3c3-397859c4d8fa)



## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
