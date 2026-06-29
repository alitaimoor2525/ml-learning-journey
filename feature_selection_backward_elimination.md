# Backward Elimination

## Introduction
Backward Elimination is a **feature selection technique** where we start with all features and remove the least important ones step by step.

---

## Concept
- Start with all features
- Remove the least important feature
- Repeat until best subset remains

---

## Steps
1. Train model with all features
2. Evaluate feature importance
3. Remove least important feature
4. Retrain model
5. Repeat until desired features remain

---

## Example (Scikit-learn)
```python
from sklearn.feature_selection import SequentialFeatureSelector
from sklearn.linear_model import LinearRegression

model = LinearRegression()

sfs = SequentialFeatureSelector(model, direction="backward", n_features_to_select=3)
sfs.fit(X, y)

selected_features = sfs.get_support()
```

---

## Advantages
- Considers full model initially
- More accurate than forward selection

---

## Disadvantages
- Computationally expensive
- Not suitable for very large datasets

---

## When to Use
- When dataset is small
- When accuracy is more important than speed

---

## Summary
Backward Elimination removes unnecessary features from a full model to improve performance.

---

**End of Notes**

