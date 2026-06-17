# Outlier Removal using IQR Method (Complete Notes)

## Introduction
Outliers are extreme values that are very different from the rest of the data. They can negatively affect machine learning models, especially regression models.

One of the most common methods to detect and remove outliers is the **IQR (Interquartile Range) method**.

---

## 1. What is IQR?

### Definition
IQR (Interquartile Range) is the difference between the third quartile (Q3) and the first quartile (Q1).

IQR = Q3 - Q1

- Q1 → 25th percentile
- Q3 → 75th percentile

---

## 2. Outlier Detection Rule

Lower Bound = Q1 - 1.5 * IQR  
Upper Bound = Q3 + 1.5 * IQR

- Values below lower bound → Outliers
- Values above upper bound → Outliers

---

## 3. Implementation in Pandas

### Step 1: Calculate Q1 and Q3
```python
Q1 = df['column_name'].quantile(0.25)
Q3 = df['column_name'].quantile(0.75)
```

### Step 2: Calculate IQR
```python
IQR = Q3 - Q1
```

### Step 3: Define bounds
```python
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
```

### Step 4: Remove outliers
```python
df = df[(df['column_name'] >= lower_bound) & (df['column_name'] <= upper_bound)]
```

---

## 4. Example

```python
import pandas as pd

data = {'Salary': [20000, 25000, 30000, 1000000]}

df = pd.DataFrame(data)

Q1 = df['Salary'].quantile(0.25)
Q3 = df['Salary'].quantile(0.75)

IQR = Q3 - Q1

lower = Q1 - 1.5 * IQR
upper = Q3 + 1.5 * IQR

# Remove outliers
df = df[(df['Salary'] >= lower) & (df['Salary'] <= upper)]
```

---

## 5. Important Notes

- Works best for numerical data
- Good for skewed data
- Does not assume normal distribution
- Removes extreme values safely

---

## 6. Quick Revision

- IQR = Q3 - Q1
- Lower = Q1 - 1.5 * IQR
- Upper = Q3 + 1.5 * IQR
- Filter data between bounds

---

(End of Notes)

