# 📅 Day 2 – Two Pointers Pattern

## In this day, we learn one of the most powerful array techniques used in interviews — **Two Pointers**.

---

## ✅ Problem 1: Two Sum in a Sorted Array

---

### 🏢 Asked In

`Amazon` `Microsoft` `Google` `Facebook`

---

### 📌 Problem Statement
Given a sorted array of integers and a target value, determine whether there exist two numbers such that their sum equals the target.

Return `True` if such a pair exists, otherwise return `False`.

---

### 💡 Approach

Since the array is sorted, we can use two pointers:

- One pointer at the beginning.
- One pointer at the end.

We adjust pointers based on the sum comparison.

---

### 🧠 Detailed Explanation

1. Initialize two pointers:
   - `left = 0`
   - `right = len(arr) - 1`
2. Calculate the sum of elements at both pointers.
3. If sum equals target → return True.
4. If sum is less than target → move left pointer forward.
5. If sum is greater than target → move right pointer backward.
6. Continue until left < right.
7. If no pair found → return False.

This works because the array is sorted.

---

### 💻 Solution (Python)

```python
def two_sum_sorted(arr, target):
    left = 0
    right = len(arr) - 1

    while left < right:
        current_sum = arr[left] + arr[right]

        if current_sum == target:
            return True
        elif current_sum < target:
            left += 1
        else:
            right -= 1

    return False
```
---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Each element is visited at most once.
Space Complexity: O(1) : No additional data structures used.

---

## ✅ Problem 2: Remove Duplicates from Sorted ArrayReverse an Array

---

### 🏢 Asked In

`Amazon` `Apple` `Google`

---

### 📌 Problem Statement
Given a sorted array, remove duplicates in-place such that each element appears only once. Return the number of unique elements.

---

### 💡 Approach

Use two pointers:

- One pointer (i) keeps track of unique position.
- Another pointer (j) scans the array.

---

### 🧠 Detailed Explanation

1. If the array is empty → return 0.
2. Set pointer i = 0.
3. Traverse from index 1 to end using pointer j.
4. If arr[j] is different from arr[i]:
    - Increment i
    - Assign arr[i] = arr[j]
5. After traversal, return i + 1.
This ensures duplicates are overwritten.

---

### 💻 Solution (Python)

```python
def remove_duplicates(arr):
    if not arr:
        return 0

    i = 0
    for j in range(1, len(arr)):
        if arr[j] != arr[i]:
            i += 1
            arr[i] = arr[j]

    return i + 1
```

---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Single traversal of the array.
Space Complexity: O(1) : In-place modification without extra space.

### 🎯 Day 2 Completed Successfully! Practice both problems before moving to Day 3.