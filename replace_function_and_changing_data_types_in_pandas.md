# Replace Function & Changing Data Types in Pandas (Complete Notes)

## Introduction
In data preprocessing, we often need to **replace values** and **change data types** to make data suitable for analysis and machine learning models.

---

## 1. Replace Function in Pandas

### Definition
`replace()` is used to replace specific values in a dataset with new values.

---

## 2. Basic Syntax

```python
df['column_name'].replace(old_value, new_value)
```

---

## 3. Examples

### a) Replace single value
```python
df['Gender'] = df['Gender'].replace('Male', 1)
```

### b) Replace multiple values
```python
df['Gender'] = df['Gender'].replace({'Male': 1, 'Female': 0})
```

### c) Replace entire dataset values
```python
df.replace({'Yes': 1, 'No': 0}, inplace=True)
```

---

## 4. Important Notes (replace)

- Works on column or entire DataFrame
- Can replace single or multiple values
- Useful for encoding simple categories

---

## 5. Changing Data Types

### Why Change Data Types?

- Ensure correct calculations
- Improve memory usage
- Required for ML models

---

## 6. Using astype()

### Syntax
```python
df['column_name'] = df['column_name'].astype(new_type)
```

---

## 7. Examples

### a) Convert to integer
```python
df['Age'] = df['Age'].astype(int)
```

### b) Convert to float
```python
df['Salary'] = df['Salary'].astype(float)
```

### c) Convert to string
```python
df['Name'] = df['Name'].astype(str)
```

---

## 8. Handling Errors

### Convert safely using to_numeric
```python
pd.to_numeric(df['column_name'], errors='coerce')
```

- Invalid values → converted to NaN

---

## 9. Important Notes (Data Types)

- astype() may give error if data is invalid
- Use `errors='coerce'` to handle bad data
- Always check data using `df.info()`

---

## 10. Quick Revision

- replace() → change values
- astype() → change data type
- to_numeric() → safe conversion

---

(End of Notes)

