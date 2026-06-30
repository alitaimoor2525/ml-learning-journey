# Cost Function and Its Types

## Introduction
A **cost function** (also called loss function) measures how well a machine learning model is performing.

- It calculates the difference between **actual values (y)** and **predicted values (ŷ)**
- Goal of model → **minimize the cost function**

---

## Why Cost Function?
- Helps evaluate model performance
- Guides optimization (e.g., Gradient Descent)
- Lower cost = better model

---

## 1. Mean Squared Error (MSE)

genui{"math_block_widget_always_prefetch_v2": {"content": "MSE = \frac{1}{n} \sum (y_i - \hat{y}_i)^2"}}

### Features
- Squares the error
- Penalizes large errors more

### Use Case
- Regression problems

---

## 2. Mean Absolute Error (MAE)

genui{"math_block_widget_always_prefetch_v2": {"content": "MAE = \frac{1}{n} \sum |y_i - \hat{y}_i|"}}

### Features
- Takes absolute difference
- Less sensitive to outliers

### Use Case
- Regression problems

---

## 3. Root Mean Squared Error (RMSE)

genui{"math_block_widget_always_prefetch_v2": {"content": "RMSE = \sqrt{\frac{1}{n} \sum (y_i - \hat{y}_i)^2}"}}

### Features
- Square root of MSE
- Same unit as target variable

### Use Case
- Regression problems

---

## 4. Binary Cross Entropy (Log Loss)

genui{"math_block_widget_always_prefetch_v2": {"content": "L = -\frac{1}{n} \sum [y \log(\hat{y}) + (1-y) \log(1-\hat{y})]"}}

### Features
- Used for binary classification
- Penalizes wrong confident predictions

---

## 5. Categorical Cross Entropy

genui{"math_block_widget_always_prefetch_v2": {"content": "L = -\sum y_i \log(\hat{y}_i)"}}

### Features
- Used for multi-class classification

---

## Difference Between Cost & Loss
- **Loss Function** → error for one data point
- **Cost Function** → average loss over dataset

---

## Key Points
- Objective of ML → minimize cost function
- Different problems use different cost functions
- Choice of cost function affects model performance

---

## Summary
Cost functions are essential in machine learning as they measure error and guide the model toward better predictions.

---

**End of Notes**

