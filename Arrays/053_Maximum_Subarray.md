# 53. Maximum Subarray

## Problem

Given an integer array `nums`, find the contiguous subarray with the largest sum and return its sum.

**LeetCode:** 53 - Maximum Subarray

---

## Difficulty

**Medium**

---

## Approach

### Idea

Use **Kadane's Algorithm**.

At every element, there are only two choices:

1. Start a new subarray from the current element.
2. Extend the previous subarray.

Choose whichever gives the larger sum.

---

## Algorithm

1. Initialize:

   * `cur = nums[0]`
   * `best = nums[0]`
2. Traverse the remaining elements.
3. Update the current subarray sum:

   ```python
   cur = max(i, cur + i)
   ```
4. Update the maximum sum found:

   ```python
   best = max(best, cur)
   ```
5. Return `best`.

---

## Python Solution

```python
class Solution(object):
    def maxSubArray(self, nums):
        cur = nums[0]
        best = nums[0]

        for i in nums[1:]:
            cur = max(i, cur + i)
            best = max(best, cur)

        return best
```

---

## Time Complexity

* **Time:** `O(n)`
* **Space:** `O(1)`

---

## Key Learning

Kadane's Algorithm is based on one simple decision:

> **Should I start a new subarray here, or continue the previous one?**

Mathematically:

```python
cur = max(current_element, current_sum + current_element)
```

The variable `cur` always represents the **maximum subarray sum ending at the current index**, while `best` stores the **maximum subarray sum found anywhere in the array**.

---

## Mistakes I Made While Learning

* Initially reset the running sum to `0`, which failed for arrays containing all negative numbers.
* Compared `cur` with `cur + i` instead of comparing `i` with `cur + i`.
* Forgot to update `best` after restarting a new subarray.
* Learned that the decision should always be:

  * **Start new:** `i`
  * **Continue:** `cur + i`

---

## Pattern Recognition

Use Kadane's Algorithm when a problem asks for:

* Maximum sum of a contiguous subarray
* Best continuous profit or gain
* Largest continuous score
* Maximum contiguous sequence

The common pattern is:

```
Current Answer
      ↓
Restart or Continue
      ↓
Update Global Best
```

---

## Revision Notes

* `cur` = Best subarray ending at the current index.
* `best` = Best subarray found so far.
* Compare only:

  * `i`
  * `cur + i`
* Update `best` after every iteration.

---

## Status

* ✅ Solved independently
* ✅ Understood Kadane's Algorithm
* ✅ Optimal Solution (O(n) Time, O(1) Space)
* 🔄 Recommended for revision after 1 day, 7 days, and 30 days.
