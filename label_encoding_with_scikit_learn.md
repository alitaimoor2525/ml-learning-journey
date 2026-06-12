# Label Encoding with Scikit-learn (Complete Notes)

## Introduction
Label Encoding is used to convert categorical labels into numerical form. Each unique category is assigned a unique integer value.

---

## 1. What is Label Encoding?

### Definition
Label Encoding converts categorical values into numeric labels.

### Example
Category → Dog, Cat, Cow

After encoding:
- Dog → 0
- Cat → 1
- Cow → 2

---

## 2. When to Use Label Encoding?

- When categories have **no meaningful order** (but model can handle it)
- Commonly used for **target variable (y)**

⚠️ Not ideal for input features with many categories (use One Hot Encoding instead)

---

## 3. Importing LabelEncoder

```python
from sklearn.preprocessing import LabelEncoder
```

---

## 4. Using LabelEncoder

### Step 1: Create object
```python
le = LabelEncoder()
```

### Step 2: Fit and Transform
```python
df['column_name'] = le.fit_transform(df['column_name'])
```

---

## 5. Understanding fit() and transform()

### fit()
- Learns unique categories from data

### transform()
- Converts categories into numbers

### fit_transform()
- Performs both steps together

```python
le.fit(df['column_name'])
le.transform(df['column_name'])
```

---

## 6. Transform New Data

```python
new_data = ['Dog', 'Cow']
le.transform(new_data)
```

⚠️ Important: New data must contain **only previously seen categories**

---

## 7. Inverse Transform (Back to Original)

```python
le.inverse_transform([0, 1, 2])
```

---

## 8. Important Notes

- LabelEncoder works on **1D data (single column)**
- It assigns numbers **based on alphabetical order**
- Be careful: Model may assume order exists

---

## Quick Revision

- Label Encoding → categorical to numbers
- fit() → learn categories
- transform() → apply encoding
- fit_transform() → both steps

---

(End of Notes)

