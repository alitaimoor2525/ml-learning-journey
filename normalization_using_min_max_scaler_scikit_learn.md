# Normalization using MinMaxScaler (Scikit-learn)

## Introduction
Normalization is a feature scaling technique that transforms data into a fixed range, usually between **0 and 1**. It is very useful when features have different scales.

---

## 1. What is Normalization?

### Definition
Normalization rescales data to a specific range.

Formula:
X_scaled = (X - X_min) / (X_max - X_min)

---

## 2. Why Use Normalization?

- Ensures all features are on the same scale
- Important for distance-based algorithms (KNN, K-Means)
- Prevents dominance of large-value features

---

## 3. Using MinMaxScaler (Scikit-learn)

### Import
```python
from sklearn.preprocessing import MinMaxScaler
```

---

## 4. Implementation

### Step 1: Create scaler
```python
scaler = MinMaxScaler()
```

### Step 2: Fit and transform training data
```python
X_train_scaled = scaler.fit_transform(X_train)
```

### Step 3: Transform test data
```python
X_test_scaled = scaler.transform(X_test)
```

---

## 5. Example

```python
import pandas as pd
from sklearn.preprocessing import MinMaxScaler

# Sample data
df = pd.DataFrame({'Age': [20, 25, 30, 35, 40]})

scaler = MinMaxScaler()

df['Age_scaled'] = scaler.fit_transform(df[['Age']])
```

---

## 6. Feature Range (Custom Range)

```python
scaler = MinMaxScaler(feature_range=(0, 1))
```

You can also change range:
```python
scaler = MinMaxScaler(feature_range=(0, 10))
```

---

## 7. Important Concepts

- fit() → learns min and max from training data
- transform() → applies scaling
- fit_transform() → both together

⚠️ Always fit only on training data

---

## 8. When to Use MinMaxScaler?

- KNN
- K-Means
- Neural Networks

---

## 9. Advantages

- Keeps data within fixed range
- Preserves original distribution shape

---

## 10. Disadvantages

- Sensitive to outliers

---

## Quick Revision

- Normalization → scale between 0 and 1
- Formula uses min and max
- Use MinMa