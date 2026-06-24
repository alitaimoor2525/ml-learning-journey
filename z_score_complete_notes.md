# Z-Score (Standard Score) – Complete Notes

## Introduction
Z-Score is a statistical measurement that tells how far a data point is from the mean in terms of standard deviations. It is widely used in Machine Learning for **outlier detection** and **data standardization**.

---

## 1. Z-Score Formula

Z = (X - Mean) / Standard Deviation

Where:
- X → Data point
- Mean → Average of dataset
- Standard Deviation → Spread of data

---

## 2. Interpretation of Z-Score

| Z-Score | Meaning |
|--------|--------|
| 0 | Exactly at mean |
| +1 | 1 std above mean |
| -1 | 1 std below mean |
| +2 | Far above mean |
| -2 | Far below mean |
| > +3 or < -3 | Outlier |

---

## 3. 3-Sigma Rule (Outlier Detection)

- Most data lies between -3 and +3
- If Z > 3 or Z < -3 → Outlier

---

## 4. Why Use Z-Score?

- Detect outliers
- Normalize data
- Compare values from different datasets

---

## 5. Implementation in Python (Pandas + NumPy)

```python
import pandas as pd
import numpy as np

# Sample data
df = pd.DataFrame({'Marks': [40, 50, 60, 70, 100]})

# Mean and Std
mean = df['Marks'].mean()
std = df['Marks'].std()

# Z-score
z = (df['Marks'] - mean) / std
```

---

## 6. Removing Outliers using Z-Score

```python
df = df[(z > -3) & (z < 3)]
```

---

## 7. Using SciPy

```python
from scipy import stats

z = np.abs(stats.zscore(df['Marks']))

df = df[z < 3]
```

---

## 8. Z-Score for Standardization (Feature Scaling)

Z-score is also used in scaling:

- Converts data to mean = 0
- Standard deviation = 1

---

## 9. Advantages

- Simple and easy to calculate
- Useful for normally distributed data
- Helps in outlier detection

---

## 10. Disadvantages

- Sensitive to extreme values
- Not suitable for skewed data

---

## 11. Important Notes

- Works best when data is normally distributed
- Always check distribution before applying
- Combine with visualization (histogram/boxplot)

---

## Quick Revision

- Z = (X - Mean) / Std
- Range: -3 to +3 (normal data)
- Outside → Outliers
- Used for detection + scaling

---

(End of Notes)

