# Feature Scaling using Standardization (StandardScaler)

## Introduction
Feature Scaling is used to bring all features to a similar scale. **Standardization** is one of the most important scaling techniques used in Machine Learning.

---

## 1. What is Standardization?

### Definition
Standardization transforms data so that:
- Mean = 0
- Standard Deviation = 1

Formula:
Z = (X - Mean) / Standard Deviation

---

## 2. Why Use Standardization?

- Improves model performance
- Required for distance-based algorithms (KNN, SVM)
- Helps gradient-based algorithms converge faster

---

## 3. Using StandardScaler (Scikit-learn)

### Import
```python
from sklearn.preprocessing import StandardScaler
```

---

## 4. Implementation

### Step 1: Create scaler object
```python
scaler = StandardScaler()
```

### Step 2: Fit and Transform training data
```python
X_train_scaled = scaler.fit_transform(X_train)
```

### Step 3: Transform test data
```python
X_test_scaled = scaler.transform(X_test)
```

---

## 5. Important Concept

- fit() → learns mean and std from training data
- transform() → applies scaling
- fit_transform() → both steps together

⚠️ Always fit only on training data, not on test data

---

## 6. Example

```python
import pandas as pd
from sklearn.preprocessing import StandardScaler

# Sample data
df = pd.DataFrame({'Age': [20, 25, 30, 35, 40]})

scaler = StandardScaler()

df['Age_scaled'] = scaler.fit_transform(df[['Age']])
```

---

## 7. When to Use StandardScaler?

- KNN
- SVM
- Logistic Regression
- Linear Regression

---

## 8. Advantages

- Centers data around 0
- Works well with normally distributed data

---

## 9. Disadvantages

- Sensitive to outliers

---

## Quick Revision

- Standardization → mean = 0, std = 1
- Use StandardScaler
- fit on train, transform on test

---

(End of Notes)

