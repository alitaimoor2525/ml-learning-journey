# Train-Test Split (Scikit-learn)

## Introduction
Train-test split is a technique used to divide a dataset into two parts:
- **Training set** → used to train the model
- **Testing set** → used to evaluate the model

---

## Why Use Train-Test Split?
- Prevents overfitting
- Evaluates model performance on unseen data
- Simulates real-world predictions

---

## Import
```python
from sklearn.model_selection import train_test_split
```

---

## Basic Syntax
```python
X_train, X_test, y_train, y_test = train_test_split(X, y)
```

---

## With Parameters
```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y,
    test_size=0.2,
    random_state=42,
    shuffle=True
)
```

---

## Parameters Explained

| Parameter | Description |
|----------|------------|
| test_size | Percentage of data for testing (e.g., 0.2 = 20%) |
| train_size | Size of training data (optional) |
| random_state | Ensures reproducibility |
| shuffle | Shuffles data before splitting |

---

## Example
```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.25, random_state=1
)
```

---

## Important Notes
- Always split data before training the model
- Never train on test data ❌
- Use same random_state for consistent results

---

## Train-Test Ratio

| Ratio | Use Case |
|------|--------|
| 80:20 | Most common |
| 70:30 | Small datasets |
| 90:10 | Large datasets |

---

## Summary
Train-test split helps evaluate machine learning models on unseen data and ensures better generalization.

---

**End of Notes**

