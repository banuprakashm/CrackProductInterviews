# 📅 Day 3 – Sliding Window Pattern

## In this day, we learn the **Sliding Window technique**, which helps optimize problems involving subarrays or continuous sequences.

---

## ✅ Problem 1: Maximum Sum Subarray of Size K

---

### 📌 Problem Statement
Given an array of integers and a number `k`, find the maximum sum of any contiguous subarray of size `k`.

---

### 💡 Approach

Instead of calculating every subarray sum repeatedly (which is inefficient), we use a sliding window:

- Calculate sum of first `k` elements.
- Slide the window forward by removing the left element and adding the new right element.

---

### 🧠 Detailed Explanation

1. Compute the sum of first `k` elements.
2. Store it as `max_sum`.
3. Start from index `k`.
4. Add current element to window.
5. Subtract element that is leaving the window.
6. Update `max_sum`.
7. Continue until end of array.

This reduces unnecessary repeated summation.


---

### 💻 Solution (Python)

```python
def max_subarray_sum(arr, k):
    window_sum = sum(arr[:k])
    max_sum = window_sum

    for i in range(k, len(arr)):
        window_sum += arr[i]
        window_sum -= arr[i - k]
        max_sum = max(max_sum, window_sum)

    return max_sum
```
---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Each element is processed once.
Space Complexity: O(1) : Only variables are used.

---

## ✅ Problem 2: Longest Substring Without Repeating Characters

---

### 📌 Problem Statement
Given a string, find the length of the longest substring without repeating characters.

---

### 💡 Approach

Use sliding window with a set:

- Expand window by adding characters.
- If duplicate found, shrink from left.
- Track maximum length.

---

### 🧠 Detailed Explanation

1. Use two pointers left and right.
2. Maintain a set to track characters in window.
3. If character not in set → add it.
4. If duplicate found → remove from left until unique.
5. Update maximum length during traversal.

---

### 💻 Solution (Python)

```python
def length_of_longest_substring(s):
    char_set = set()
    left = 0
    max_length = 0

    for right in range(len(s)):
        while s[right] in char_set:
            char_set.remove(s[left])
            left += 1

        char_set.add(s[right])
        max_length = max(max_length, right - left + 1)

    return max_length
```

---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Each character is visited at most twice.
Space Complexity: O(min(n, m)) : Set stores unique characters.

### 🎯 Day 3 Completed Successfully! Practice both problems before moving to Day 4.