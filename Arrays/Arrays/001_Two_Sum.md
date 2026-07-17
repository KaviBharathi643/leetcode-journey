# 001. Two Sum

**LeetCode:** https://leetcode.com/problems/two-sum/

* **Difficulty:** Easy
* **Topic:** Arrays, Hash Map
* **Pattern:** Hash Map Lookup

---

## Problem Summary

Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to the target.

---

## Approach

* Traverse the array once.
* Store each number and its index in a hash map.
* For every element, calculate its complement (`target - current_number`).
* If the complement already exists in the hash map, return the stored index and the current index.

---

## Complexity

* **Time Complexity:** O(n)
* **Space Complexity:** O(n)

---

## Key Learning

* Hash maps reduce the search time from **O(n²)** to **O(n)**.
* Store previously visited elements to avoid nested loops.
* This is one of the most common interview patterns.

---

## Mistakes I Made

* Initially solved it using list slicing and `index()`, which resulted in **O(n²)** time complexity.
* Modified the input array unnecessarily.
* Learned why the hash map approach is the preferred interview solution.

---

## Revision Notes

* Think: **"Need to find a previously seen value quickly?" → Use a Hash Map.**
* Avoid brute-force nested loops unless specifically required.

---

## Status

* ✅ Solved
* ⭐ Confidence: 4/5
