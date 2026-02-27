# 📅 Strings – Day 3 - Sliding Window Pattern

## In this day, we apply the Sliding Window technique to solve advanced string problems efficiently.
---

## ✅ Problem 1:  Longest Substring Without Repeating Characters
---

### 📌 Problem Statement
Given a string `s`, find the length of the longest substring without repeating characters.

---

### 💡 Approach

Use a sliding window with two pointers and a set.

- Expand the window using right pointer.
- If duplicate character appears, shrink window from left.
- Track maximum window length.

---

### 🧠 Detailed Explanation

1. Initialize:
   - `left = 0`
   - An empty set to track characters.
2. Move `right` pointer through string.
3. If character not in set:
   - Add it to set.
   - Update max length.
4. If character already exists:
   - Remove characters from left until duplicate is removed.
5. Continue until end of string.

Each character is added and removed at most once.

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

---

## ✅ Problem 2: Longest Repeating Character Replacement

---

### 📌 Problem Statement
Given a string s and an integer k, you can replace at most k characters. Return the length of the longest substring containing the same letter after replacement.

---

### 💡 Approach

Use sliding window with a frequency map.
1. Maintain window size.
2. Track most frequent character in window.
3. If window size - max frequency > k → shrink window.

---

### 🧠 Detailed Explanation

1. Use dictionary to count character frequency.
2. Maintain:
   - left pointer
   - max_freq (maximum frequency in window)
3. Expand right pointer.
4. If window size - max_freq > k:
   - Shrink from left.
   - Update maximum length.

5. The key insight: We allow up to k replacements, so window is valid if:
(window size - most frequent char count) ≤ k


---

### 💻 Solution (Python)

```python
def character_replacement(s, k):
    count = {}
    left = 0
    max_freq = 0
    max_length = 0

    for right in range(len(s)):
        count[s[right]] = count.get(s[right], 0) + 1
        max_freq = max(max_freq, count[s[right]])

        while (right - left + 1) - max_freq > k:
            count[s[left]] -= 1
            left += 1

        max_length = max(max_length, right - left + 1)

    return max_length
```

---

### ⏱ Time & Space Complexity

Time Complexity: O(n) : Single pass with sliding window.
Space Complexity: O(1) : At most 26 uppercase characters stored.

---

### 🎯 Day 3 Completed Successfully! Practice both problems before moving to Day 4.
