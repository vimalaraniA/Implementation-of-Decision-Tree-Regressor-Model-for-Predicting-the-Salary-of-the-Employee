# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee
Developed by: VIMALA RANI A

RegisterNumber: 212223040240


## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. *Load Data* – Import the dataset containing employee details and their salaries.

2. *Preprocess Data* – Handle missing values, encode categorical variables, and split into training and test sets.

3. *Initialize Model* – Create a DecisionTreeRegressor with suitable parameters (e.g., max_depth=5).

4. *Train Model* – Fit the regressor using training data (model.fit(X_train, y_train)).

5. *Predict & Evaluate* – Predict salaries on test data and evaluate using metrics like MAE, MSE, and R² score.

6. *Visualize & Interpret* – Plot the tree and analyze feature importance for salary prediction.
   
## Program & Output:

Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

import pandas as pd
data=pd.read_csv("C:\\Users\\admin\\OneDrive\\Desktop\\Folders\\ML\\DATASET-20250226\\Salary.csv")
data.head()

![image](https://github.com/user-attachments/assets/fb7e5837-fa27-4dd2-9fc8-87b5072ac334)


data.info()
data.isnull().sum()

![image](https://github.com/user-attachments/assets/e898c62f-8a56-4b06-9149-7b960db1ea02)


from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

![image](https://github.com/user-attachments/assets/b7b88868-579e-498d-9114-e41159ff1733)


x=data[["Position","Level"]]
x.head()
y=data["Salary"]
y.head()

![image](https://github.com/user-attachments/assets/af7af4d2-82a1-4f1f-88e7-6f2347954aeb)


from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred

![image](https://github.com/user-attachments/assets/06fd2d05-c429-4c48-83e1-6038dbe82145)


from sklearn import metrics
from sklearn.metrics import r2_score
r2 = r2_score(y_test, y_pred)
r2

![image](https://github.com/user-attachments/assets/3f40d399-0f10-4ab7-8117-86ab06f5c8b1)

dt.predict([[5,6]])


![image](https://github.com/user-attachments/assets/5bddfaf6-ef95-4654-8526-11fea921f807)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
