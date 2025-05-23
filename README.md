# Implementation-of-Logistic-Regression-Using-Gradient-Descent

## AIM:
To write a program to implement the the Logistic Regression Using Gradient Descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries.
2. Load the dataset and print the values.
3. Define X and Y array and display the value.
4. Find the value for cost and gradient.
5. Plot the decision boundary and predict the Regression value. 

## Program and Output:
```
/*
Program to implement the the Logistic Regression Using Gradient Descent.
Developed by: Shree Lekha.S
RegisterNumber: 212223110052
*/
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

dataset = pd.read_csv('Placement_Data.csv')
dataset

```
![image](https://github.com/user-attachments/assets/cc162845-f890-43aa-ac72-383d367aa310)
```
dataset = dataset.drop('sl_no',axis=1)
dataset = dataset.drop('salary',axis=1)

dataset["gender"] = dataset["gender"].astype('category')
dataset["ssc_b"] = dataset["ssc_b"].astype('category')
dataset["hsc_b"] = dataset["hsc_b"].astype('category')
dataset["degree_t"] = dataset["degree_t"].astype('category')
dataset["workex"] = dataset["workex"].astype('category')
dataset["specialisation"] = dataset["specialisation"].astype('category')
dataset["status"] = dataset["status"].astype('category')
dataset["hsc_s"] = dataset["hsc_s"].astype('category')

dataset.dtypes

```
![image](https://github.com/user-attachments/assets/489d8e86-d05c-471d-ba83-0a77b7cab044)

```
dataset["gender"] = dataset["gender"].cat.codes
dataset["ssc_b"] = dataset["ssc_b"].cat.codes
dataset["hsc_b"] = dataset["hsc_b"].cat.codes
dataset["degree_t"] = dataset["degree_t"].cat.codes
dataset["workex"] = dataset["workex"].cat.codes
dataset["specialisation"] = dataset["specialisation"].cat.codes
dataset["status"] = dataset["status"].cat.codes
dataset["hsc_s"] = dataset["hsc_s"].cat.codes

dataset

```
![image](https://github.com/user-attachments/assets/a5388cb1-fb29-466f-ba0d-b9efb8de4e18)
```
X = dataset.iloc[:, :-1].values
Y = dataset.iloc[:,-1].values

Y
```

![image](https://github.com/user-attachments/assets/cc4e45f4-2f67-44a9-b1fe-851871185ca9)

```
theta = np.random.randn(X.shape[1])
y=Y

def sigmoid(z):
  return 1 / (1 + np.exp(-z))

def gradient_descent(theta, X, y, alpha, num_iterations):
  m = len(y)
  for i in range(num_iterations):
    h = sigmoid(X.dot(theta))
    gradient = X.T.dot(h - y) / m
    theta -= alpha * gradient
  return theta

theta = gradient_descent(theta, X, y, alpha=0.01, num_iterations=1000)

def predict(theta, X):
  h = sigmoid(X.dot(theta))
  y_pred = np.where(h >= 0.5,1, 0)
  return y_pred

y_pred = predict(theta, X)
accuracy = np.mean(y_pred.flatten() == y)

print("Accuracy", accuracy)

```
![image](https://github.com/user-attachments/assets/9bb5a5d1-518f-4347-9f0f-58840b267c7b)

```

print(y_pred)
```
![image](https://github.com/user-attachments/assets/6bddc509-a868-4a57-af9a-82c21d345239)

```
print(Y)
```
![image](https://github.com/user-attachments/assets/0fef0550-976c-4afe-a20c-b106a0cec89d)

```
xnew = np.array([[0, 87, 0, 95, 0, 2, 78, 2, 0, 0, 1, 0]])
y_prednew = predict (theta, xnew)
print(y_prednew)
```
![image](https://github.com/user-attachments/assets/cfd4c9fb-3edd-4ff4-b7cc-bb9ec7674c40)

```
xnew = np.array([[0, 0, 0, 0, 0, 2, 8, 2, 0, 0, 1, 0]])
y_prednew = predict (theta, xnew)
print(y_prednew)
```
![image](https://github.com/user-attachments/assets/b0359bd4-41ee-4b5d-af99-161a6e643c4e)

## Result:
Thus the program to implement the the Logistic Regression Using Gradient Descent is written and verified using python programming.

