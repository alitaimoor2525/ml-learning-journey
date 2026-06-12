# One Hot Encoding & Data Transformation (Complete Notes)

## Introduction
Categorical data must be converted into numerical form before applying Machine Learning algorithms. One of the most common techniques is **One Hot Encoding**.

---

## 1. One Hot Encoding

### Definition
One Hot Encoding converts categorical variables into binary (0/1) columns.

### Example
Color → Red, Blue, Green

After encoding:
- Red → [1, 0, 0]
- Blue → [0, 1, 0]
- Green → [0, 0, 1]

---

## 2. Using Pandas (get_dummies)

### Syntax
```python
import pandas as pd

pd.get_dummies(df['column_name'])
```

### Example
```python
df = pd.DataFrame({'Color': ['Red', 'Blue', 'Green']})

pd.get_dummies(df['Color'])
```

---

## 3. Dummy Variables

- The new columns created after encoding are called **dummy variables**
- Each column represents one category

---

## 4. Dropping First Column (Dummy Variable Trap)

### Problem
If we create all dummy variables, it may cause **multicollinearity** (redundancy)

### Solution
Drop one column:
```python
pd.get_dummies(df['column_name'], drop_first=True)
```

---

## 5. Using Scikit-learn (OneHotEncoder)

### Import
```python
from sklearn.preprocessing import OneHotEncoder
```

### Example
```python
encoder = OneHotEncoder(drop='first', sparse=False)

encoded = encoder.fit_transform(df[['column_name']])
```

---

## 6. Transforming Data

### fit()
- Learns categories from data

### transform()
- Converts data into encoded form

### fit_transform()
- Does both in one step

```python
encoder.fit(df[['column_name']])
encoder.transform(df[['column_name']])
```

---

## 7. Important Notes

- Always use double brackets [[ ]] for sklearn
- drop='first' helps avoid dummy variable trap
- Use pandas for quick analysis
- Use sklearn for ML pipelines

---

## Quick Revision

- One Hot Encoding → categorical to binary
- get_dummies() → pandas method
- OneHotEncoder → sklearn method
- drop_first → remove redundancy
- fit / transform → learn + apply

---

(End of Notes)

