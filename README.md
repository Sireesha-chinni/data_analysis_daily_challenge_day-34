# Day 34 – Python Coding Challenge: Built-in Functions

A set of five beginner-friendly Python problems focused on built-in functions and core data structures (`list`, `set`, `dict`), framed around real-world data analytics scenarios.

## Files

| File | Description |
|------|-------------|
| `Day34_Coding_Challenge.pdf` | Problem statements with expected outputs |
| `Day-34-Data-analytics-challenge-python.ipynb` | Jupyter notebook with my solutions |

## Requirements

- Python 3.9+
- Jupyter Notebook / JupyterLab

No third-party libraries are needed.

## How to Run

```bash
jupyter notebook Day-34-Data-analytics-challenge-python.ipynb
```

Then run the cells from top to bottom (**Cell → Run All**).

## Challenges

### 1. Remove Duplicates & Preserve Order
- **Concepts:** `set()`, `list`, loop
- **Task:** Remove duplicate student IDs from `[101, 102, 101, 103, 102, 104]`.
- **Expected output:** `[101, 102, 103, 104]`
- **My approach:** Loop through the list, add each ID to a `set`, convert back to a list and sort it.

### 2. Frequency Counter
- **Concepts:** `dict`, `get()`, loop
- **Task:** Count how many times each product was sold.
- **Expected output:** `{'apple': 3, 'banana': 2, 'orange': 1}`
- **My approach:** Build a list of unique products, then use `list.count()` to fill a dictionary with each product's count.

### 3. Find Top Scorer
- **Concepts:** `max()`, `dict`
- **Task:** Find the student with the highest marks in `{"A": 85, "B": 92, "C": 88}`.
- **Expected output:** `B`
- **My approach:** Collect the values, sort them, take the highest, then loop through the dictionary to find the matching key.

### 4. Common Elements in Two Lists
- **Concepts:** `set()`, `intersection()`
- **Task:** Find skills shared by two candidates.
- **Expected output:** `['Python', 'SQL']`
- **My approach:** Convert both lists to sets and use `intersection()`.

### 5. Sort Dictionary by Values
- **Concepts:** `sorted()`, `lambda`
- **Task:** Sort products by price.
- **Expected output:** `[('banana', 20), ('orange', 30), ('apple', 50)]`
- **My approach:** `sorted(prices.items(), key=lambda item: item[1])`

## Possible Improvements

These are alternative, more idiomatic solutions worth practicing:

```python
# 1. Preserve original order (a plain set + sort only works here because IDs happen to be ascending)
ids = [101, 102, 101, 103, 102, 104]
seen = set()
result = []
for i in ids:
    if i not in seen:
        seen.add(i)
        result.append(i)
# or: list(dict.fromkeys(ids))

# 2. Frequency counter using get() in a single pass
counts = {}
for p in products:
    counts[p] = counts.get(p, 0) + 1

# 3. Top scorer using max()
top = max(marks, key=marks.get)
```

Note that for challenge 4, `set` has no guaranteed order, so the output may come back as `['SQL', 'Python']`. Use `sorted(...)` if you need a stable order.

## What I Learned

- Using `set` for uniqueness and fast membership checks
- Building frequency tables with dictionaries
- Using `key=` with `max()` and `sorted()` to work with dictionary values
- Writing small `lambda` functions for custom sorting
- Set operations such as `intersection()`
