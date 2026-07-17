# 217. Contains Duplicate

**LeetCode:** https://leetcode.com/problems/contains-duplicate/

* **Difficulty:** Easy
* **Topic:** Arrays, Hash Set
* **Pattern:** Hash Set

---

## Problem Summary

Given an integer array `nums`, return `true` if any value appears at least twice in the array, otherwise return `false`.

---

## Approach

* Create an empty set.
* Traverse the array.
* If the current element already exists in the set, return `True`.
* Otherwise, add the element to the set.
* If no duplicates are found, return `False`.

---

## Complexity

* **Time Complexity:** O(n)
* **Space Complexity:** O(n)

---

## Key Learning

* Use a **set** when only membership checking is required.
* A set provides average **O(1)** lookup time.
* Choose the simplest data structure that satisfies the problem.

---

## Mistakes I Made

* First implemented a dictionary to count frequencies.
* Then improved it by using a dictionary only for existence checking.
* Finally realized that a **set** is the most suitable data structure.
* Also learned the concise Python solution:

```python
return len(nums) != len(set(nums))
```

---

## Revision Notes

* Need counts → Dictionary
* Need existence only → Set

---

## Status

* ✅ Solved
* ⭐ Confidence: 5/5
