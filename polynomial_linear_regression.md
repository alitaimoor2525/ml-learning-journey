# Polynomial Linear Regression

## Introduction
Polynomial Linear Regression is a type of regression where the relationship between the independent variable (X) and dependent variable (y) is modeled as a polynomial (curve) instead of a straight line.

---

## Why Polynomial Regression?
- Linear regression cannot capture non-linear patterns
- Polynomial regression helps model curved relationships

---

## Equation

genui{"math_block_widget_always_prefetch_v2": {"content": "y = b_0 + b_1x + b_2x^2 + b_3x^3 + \dots + b_nx^n"}}

---

## Explanation of Terms
- **y** → Dependent variable
- **x** → Independent variable
- **b0** → Intercept
- **b1, b2, ..., bn** → Coefficients
- **n** → Degree of polynomial

---

## Intuition
- Instead of fitting a straight line, the model fits a **curve**
- Higher degree → more flexible curve

---

## Implementation (Scikit-learn)
```python
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression

poly = PolynomialFeatures(degree=2)
X_poly = poly.fit_transform(X)

model = LinearRegression()
model.fit(X_poly, y)

y_pred = model.predict(X_poly)
```

---

## Steps
1. Convert features into polynomial features
2. Train linear regression model
3. Predict results

---

## Advantages
- Captures non-linear relationships
- Flexible model

---

## Disadvantages
- Overfitting if degree is too high
- More computational cost
- Harder to interpret

---

## When to Use
- When data shows a curved trend
- When linear regression performs poorly

---

## Important Notes
- Always choose degree carefully
- Use cross-validation to avoid overfitting

---

## Summary
Polynomial Regression extends linear regression by adding polynomial terms, allowing it to model complex relationships.

---

**End of Notes**

