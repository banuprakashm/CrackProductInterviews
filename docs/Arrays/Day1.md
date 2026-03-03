# 📅 Day 1 – Array Basics

## In this day, we focus on fundamental array operations that are commonly asked in coding interviews.
---

## ✅ Problem 1: Find Maximum Element in an Array

---

### 🏢 Asked In

`Amazon` `Microsoft` `Infosys`

---

### 📌 Problem Statement
Given an array of integers, find and return the maximum element present in the array.

---

### 💡 Approach

We traverse the array once and keep track of the largest value seen so far.

---

### 🧠 Detailed Explanation

1. Assume the first element of the array is the maximum.
2. Start traversing from the second element.
3. Compare each element with the current maximum.
4. If the current element is greater, update the maximum.
5. After finishing traversal, the stored value is the maximum element.

This avoids unnecessary sorting and gives an optimal solution.

---

### 💻 Solution (Python)

```python
def find_max(arr):
    max_element = arr[0]

    for num in arr:
        if num > max_element:
            max_element = num

    return max_element
```
---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : We scan the array once where n is number of elements.
Space Complexity: O(1) : No extra space is used.

---

## ✅ Problem 2: Reverse an Array

---

### 🏢 Asked In

`TCS` `Wipro` `Amazon`

---


### 📌 Problem Statement
Given an array, reverse the elements and return the reversed array.

---

### 💡 Approach

Use Python slicing to reverse the array.

---

### 🧠 Detailed Explanation

Python provides slicing which allows accessing elements in reverse order using [::-1].

Steps:

1. Start from last index.
2. Move backwards.
3. Collect elements into a new array.

This produces a reversed array in a single step.

---

### 💻 Solution (Python)

```python
def reverse_array(arr):
    return arr[::-1]
```

---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Each element is accessed once.
Space Complexity: O(n) : New reversed array is created.

---

### 🎯 Day 1 Completed Successfully! Practice both problems before moving to Day 2.
