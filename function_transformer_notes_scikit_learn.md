# Function Transformer (Scikit-learn) – Notes

## Introduction
`FunctionTransformer` is a utility from **scikit-learn** that allows you to apply custom transformations to your data. It is especially useful when you want to apply mathematical functions like log, square root, reciprocal, etc., as part of a preprocessing pipeline.

---

## Import
```python
from sklearn.preprocessing import FunctionTransformer
import numpy as np
```

---

## Basic Syntax
```python
transformer = FunctionTransformer(func=None)
X_transformed = transformer.fit_transform(X)
```

- `func`: function to apply on data
- `fit_transform()`: fits and applies transformation

---

## Why Use FunctionTransformer?
- Apply custom transformations
- Integrate transformations into pipelines
- Handle skewed data
- Improve model performance

---

## 1. Log Transformation
Used to reduce skewness in data.

```python
log_transformer = FunctionTransformer(np.log1p)
X_log = log_transformer.fit_transform(X)
```

**Why `log1p`?**
- Handles zero values
- Computes: log(1 + x)

---

## 2. Square Root Transformation
Used for moderate skewness.

```python
sqrt_transformer = FunctionTransformer(np.sqrt)
X_sqrt = sqrt_transformer.fit_transform(X)
```

---

## 3. Reciprocal Transformation
Useful for large values.

```python
reciprocal_transformer = FunctionTransformer(lambda x: 1 / x)
X_reciprocal = reciprocal_transformer.fit_transform(X)
```

⚠️ Avoid zero values (division error)

---

## 4. Square Transformation
Used to increase the effect of larger values.

```python
square_transformer = FunctionTransformer(np.square)
X_square = square_transformer.fit_transform(X)
```

---

## 5. Custom Function Example
You can define your own function.

```python
def custom_func(x):
    return x + 10

custom_transformer = FunctionTransformer(custom_func)
X_custom = custom_transformer.fit_transform(X)
```

---

## Using in Pipeline
```python
from sklearn.pipeline import Pipeline

pipeline = Pipeline([
    ("log_transform", FunctionTransformer(np.log1p)),
])

X_transformed = pipeline.fit_transform(X)
```

---

## Handling Negative Values
Some transformations require positive values:

```python
transformer = FunctionTransformer(lambda x: np.log1p(np.abs(x)))
```

---

## Key Points
- Works on NumPy arrays
- Can be used inside pipelines
- Helps in feature engineering
- Be careful with invalid values (e.g., log of negative numbers)

---

## When to Use Which Transformation?

| Transformation | Use Case |
|---------------|--------|
| Log           | Highly skewed data |
| Sqrt          | Moderately skewed |
| Reciprocal    | Large values |
| Square        | Emphasize large values |

---

## Summary
`FunctionTransformer` is a flexible tool for applying mathematical transformations in machine learning workflows. It helps improve data distribution and model performance when used correctly.

---

**End of Notes**

