# Handling Missing Numerical Values with Pandas

## Introduction
Missing values (NaN) are very common in real-world datasets. Proper handling is important to avoid errors and improve model performance.

---

## 1. Checking Missing Values

### a) Check null values in dataset
```python
import pandas as pd

df.isnull()
```

### b) Count null values in each column
```python
df.isnull().sum()
```

### c) Count null values in each row
```python
df.isnull().sum(axis=1)
```

---

## 2. Finding Percentage of Missing Values

### a) Column-wise percentage
```python
(df.isnull().sum() / len(df)) * 100
```

### b) Row-wise percentage
```python
(df.isnull().sum(axis=1) / df.shape[1]) * 100
```

### c) Overall dataset percentage
```python
df.isnull().sum().sum() / (df.shape[0] * df.shape[1]) * 100
```

---

## 3. Handling Missing Numerical Values

### a) Fill with Mean
```python
df['column_name'].fillna(df['column_name'].mean(), inplace=True)
```

### b) Fill with Median
```python
df['column_name'].fillna(df['column_name'].median(), inplace=True)
```

### c) Fill with Mode
```python
df['column_name'].fillna(df['column_name'].mode()[0], inplace=True)
```

---

## 4. Dropping Missing Values

### a) Drop rows with missing values
```python
df.dropna(axis=0, inplace=True)
```

### b) Drop columns with missing values
```python
df.dropna(axis=1, inplace=True)
```

### c) Drop rows with specific threshold
```python
df.dropna(thresh=3, inplace=True)
```

---

## 5. Important Notes

- Mean → good for normally distributed data
- Median → better for skewed data / outliers
- Mode → useful for categorical or repeated values
- Dropping data may cause data loss, use carefully

---

## Quick Revision

- isnull() → detect missing values
- sum() → count missing values
- fillna() → replace missing values
- dropna() → remove missing data

---

(End of Notes)

