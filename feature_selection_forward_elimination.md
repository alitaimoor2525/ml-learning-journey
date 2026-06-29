# Forward Elimination (Forward Selection)

## Introduction
Forward Elimination is a **feature selection technique** where we start with no features and add the most important features one by one.

---

## Concept
- Start with an empty model
- Add features step by step
- Choose the feature that improves model performance the most

---

## Steps
1. Initialize model with no features
2. Add one feature at a time
3. Evaluate model performance
4. Select best feature
5. Repeat until no improvement

---

## Example (Scikit-learn)
```python
from sklearn.feature_selection import SequentialFeatureSelector
from sklearn.linear_model import LinearRegression

model = LinearRegression()

sfs = SequentialFeatureSelector(model, direction="forward", n_features_to_select=3)
sfs.fit(X, y)

selected_features = sfs.get_support()
```

---

## Advantages
- Works well with large feature sets
- Reduces overfitting
- Improves model performance

---

## Disadvantages
- Can miss best combination of features
- Greedy approach (not optimal always)

---

## When to Use
- When dataset has many features
- When computational cost matters

---

## Summary
Forward Elimination builds the model step by step by adding the most useful features.

---

**End of Notes**

