# Supervised Learning with Regression

## Introduction
Supervised learning is a type of machine learning where the model is trained using labeled data (input + output).

Regression is a supervised learning technique used to predict **continuous values**.

---

## What is Regression?
Regression predicts numerical outputs such as:
- House price
- Salary
- Temperature
- Sales

---

## Types of Regression

### 1. Linear Regression
- Models relationship between input and output using a straight line

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()
model.fit(X_train, y_train)
y_pred = model.predict(X_test)
```

---

### 2. Multiple Linear Regression
- Uses multiple input features

---

### 3. Polynomial Regression
- Captures non-linear relationships

---

### 4. Ridge Regression
- Adds regularization (L2)

---

### 5. Lasso Regression
- Adds regularization (L1)

---

## Steps in Regression
1. Import dataset
2. Split data (train-test)
3. Apply feature scaling (if needed)
4. Train model
5. Predict results
6. Evaluate model

---

## Evaluation Metrics

| Metric | Description |
|-------|------------|
| MAE | Mean Absolute Error |
| MSE | Mean Squared Error |
| RMSE | Root Mean Squared Error |
| R² Score | Goodness of fit |

---

## Example (Complete Flow)
```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

model = LinearRegression()
model.fit(X_train, y_train)

y_pred = model.predict(X_test)
```

---

## Advantages
- Simple and easy to understand
- Works well with linear relationships

---

## Disadvantages
- Poor performance on complex data
- Sensitive to outliers

---

## Summary
Regression is a fundamental supervised learning technique used to predict continuous values and is widely used in real-world applications.

---

**End of Notes**

