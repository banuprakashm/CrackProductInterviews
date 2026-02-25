# 📅 Strings – Day 1 

## In this day, we focus on basic string manipulation problems frequently asked in interviews.
---

## ✅ Problem 1: Reverse a String

---

### 📌 Problem Statement
Given a string `s`, return the reversed string.

---

### 💡 Approach

Use Python slicing to reverse the string efficiently.

---

### 🧠 Detailed Explanation

Python allows slicing with `[::-1]`.

- Start from last character  
- Move backward  
- Collect characters into new string  

This gives a clean and readable solution.

---

### 💻 Solution (Python)

```python
def reverse_string(s):
    return s[::-1]
```
---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Each character is visited once.
Space Complexity: O(n) : A new reversed string is created.

---

## ✅ Problem 2: Valid Palindrome

---

### 📌 Problem Statement
Given a string `s`, determine whether it is a palindrome.

Ignore:
- Non-alphanumeric characters
- Case sensitivity

---

### 💡 Approach

1. Convert string to lowercase.
2. Remove non-alphanumeric characters.
3. Use two pointers to compare characters.

---

### 🧠 Detailed Explanation

1. Use `left` pointer at start.
2. Use `right` pointer at end.
3. Move inward.
4. If mismatch found → return False.
5. If fully traversed → return True.


---

### 💻 Solution (Python)

```python
def is_palindrome(s):
    left, right = 0, len(s) - 1

    while left < right:
        if not s[left].isalnum():
            left += 1
        elif not s[right].isalnum():
            right -= 1
        elif s[left].lower() != s[right].lower():
            return False
        else:
            left += 1
            right -= 1

    return True

```

---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Each character is visited at most once.
Space Complexity: O(1) : No extra data structures used.

---

### 🎯 Day 1 Completed Successfully! Practice both problems before moving to Day 2.
