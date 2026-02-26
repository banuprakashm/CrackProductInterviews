# 📅 Strings – Day 2 - Hashing Pattern

## In this day, we learn how to use hashing (frequency counting) to solve string problems efficiently.
---

## ✅ Problem 1:  Valid Anagram
---

### 📌 Problem Statement
Given two strings `s` and `t`, determine whether `t` is an anagram of `s`.

An anagram means both strings contain the same characters with the same frequency.

---

### 💡 Approach

Use a frequency counter (hash map).

If both strings have identical character counts → they are anagrams.

---

### 🧠 Detailed Explanation

1. If lengths of both strings are different → return False.
2. Create a dictionary to count characters in string `s`.
3. Traverse string `t`:
   - Reduce frequency for each character.
   - If character not present → return False.
4. If all counts become zero → return True.

---

### 💻 Solution (Python)

```python
def is_anagram(s, t):
    if len(s) != len(t):
        return False

    count = {}

    for char in s:
        count[char] = count.get(char, 0) + 1

    for char in t:
        if char not in count:
            return False
        count[char] -= 1
        if count[char] < 0:
            return False

    return True
```
---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Each string is traversed once.
Space Complexity: O(1) : At most 26 characters stored (for lowercase English letters).

---

## ✅ Problem 2: First Non-Repeating Character

---

### 📌 Problem Statement
Given a string s, return the index of the first non-repeating character. If none exists, return -1.

---

### 💡 Approach

1. Count frequency of each character.
2. Traverse string again.
3. Return index of first character with frequency 1.

---

### 🧠 Detailed Explanation

1. Use a dictionary to store frequency.
2. First pass → count characters.
3. Second pass → find first with count 1.
4. If none found → return -1.

This avoids nested loops and improves efficiency.


---

### 💻 Solution (Python)

```python
def first_unique_char(s):
    freq = {}

    for char in s:
        freq[char] = freq.get(char, 0) + 1

    for index, char in enumerate(s):
        if freq[char] == 1:
            return index

    return -1
```

---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Two passes through string.
Space Complexity: O(1) :Fixed character set size.

---

### 🎯 Day 2 Completed Successfully! Practice both problems before moving to Day 3.
