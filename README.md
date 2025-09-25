# PROGRAMMING-ASSIGNMENT-3

# README: Pandas Experiment – Cars Dataset

---

## Intended Learning Outcomes

1. To identify the codes and functions incorporated in the **Pandas** library.
2. To apply and use different codes and functions in creating a Python program using **Pandas**.

---

## Problem 1

### a. Load the CSV file into a DataFrame named `cars`

#### Code:

```python
import pandas as pd

cars = pd.read_csv("Cars.csv")
```

---

### b. Display the **first five** and **last five** rows of the DataFrame

#### Code:

```python
print(cars.head())
print(cars.tail())
```

---

## Problem 2

Working with the `cars` DataFrame, we perform several data selection and filtering tasks.

---

### a. Display the **first 5 rows** with **odd-numbered columns** (index 0, 2, 4…)

#### Code:

```python
cars.loc[0:4, ::2]
```

#### Output Preview:

| Model             | cyl | hp  | wt   | gear |
| ----------------- | --- | --- | ---- | ---- |
| Mazda RX4         | 6   | 110 | 2.62 | 4    |
| Mazda RX4 Wag     | 6   | 110 | 2.88 | 4    |
| Datsun 710        | 4   | 93  | 2.32 | 4    |
| Hornet 4 Drive    | 6   | 110 | 3.22 | 3    |
| Hornet Sportabout | 8   | 175 | 3.44 | 3    |

---

### b. Display the row that contains the **Model = ‘Mazda RX4’**

#### Code:

```python
cars.loc[cars['Model'] == 'Mazda RX4']
```

#### Output:

| Model     | mpg  | cyl | disp | hp  | ... | gear | carb |
| --------- | ---- | --- | ---- | --- | --- | ---- | ---- |
| Mazda RX4 | 21.0 | 6   | 160  | 110 | ... | 4    | 4    |

---

### c. How many **cylinders** does **Camaro Z28** have?

#### Code:

```python
cars.loc[cars['Model'] == 'Camaro Z28', ['cyl']]
```

#### Output:

```
cyl
8
```

---

### d. Use `.loc` to display the **cylinders** and **gear** of the following models:

* Mazda RX4 Wag
* Ford Pantera L
* Honda Civic

#### Code:

```python
result = cars.loc[
    cars['Model'].isin(['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']),
    ['Model', 'cyl', 'gear']
]
print(result)
```

#### Output:

| Model          | cyl | gear |
| -------------- | --- | ---- |
| Mazda RX4 Wag  | 6   | 4    |
| Ford Pantera L | 8   | 5    |
| Honda Civic    | 4   | 4    |

---

## Summary

| Task                     | Concept Demonstrated         |
| ------------------------ | ---------------------------- |
| Read CSV file            | `pd.read_csv()`              |
| View first/last rows     | `.head()`, `.tail()`         |
| Select specific columns  | `.iloc`, `.loc`, slicing     |
| Filter rows by condition | Boolean indexing with `.loc` |
| Match multiple values    | `.isin([...])`               |

---

