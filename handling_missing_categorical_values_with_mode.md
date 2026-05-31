# Handling Missing Categorical Values with Mode

## Introduction
Categorical data contains labels (e.g., Gender, City, Color). Missing values in such data cannot be handled using mean or median, so we use **mode (most frequent value)**.

---

## 1. What is Mode?

### Definition
Mode is the value that appears most frequently in a column.

**Example:**
Gender → Male, Female, Male, Male → Mode = Male

---

## 2. Why Use Mode for Categorical Data?

- Categorical data has no numerical meaning
- Mean/Median cannot be applied
- Mode preserves the most common category

---

## 3. Finding Mode in Pandas

```python
df['column_name'].mode()
```

### Access first mode value
```python
df['column_name'].mode()[0]
```

---

## 4. Filling Missing Values with Mode

```python
df['column_name'].fillna(df['column_name'].mode()[0], inplace=True)
```

---

## 5. Example

```python
import pandas as pd

data = {
    'City': ['Lahore', 'Karachi', None, 'Lahore', 'Karachi', None]
}

df = pd.DataFrame(data)

# Fill missing values with mode
df['City'].fillna(df['City'].mode()[0], inplace=True)
```

---

## 6. Important Notes

- Mode works best when one category is clearly dominant
- If multiple modes exist, pandas returns all → we usually take the first
- Always check distribution before applying

---

## Quick Revision

- Mode = most frequent value
- Used for categorical data