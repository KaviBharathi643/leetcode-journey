# 121. Best Time to Buy and Sell Stock

## 📌 Problem

You are given an array `prices` where `prices[i]` is the price of a stock on the `iᵗʰ` day.

Choose a single day to buy one stock and a different future day to sell it. Return the maximum profit you can achieve. If no profit is possible, return `0`.

**Difficulty:** Easy

---

## 🧠 Approach

Use the **Running Minimum + Greedy** approach.

While traversing the array:

* Keep track of the **minimum stock price seen so far**.
* Calculate the profit if the stock is sold today.
* Update the maximum profit whenever a better profit is found.

---

## 💡 Intuition

Maintain two variables:

* **min_price** → Lowest stock price seen so far.
* **max_profit** → Maximum profit found so far.

For every price:

```python
min_price = min(min_price, price)
profit = price - min_price
max_profit = max(max_profit, profit)
```

---

## ✅ Python Solution

```python
class Solution(object):
    def maxProfit(self, prices):
        min_price = prices[0]
        max_profit = 0

        for price in prices:
            min_price = min(min_price, price)
            profit = price - min_price
            max_profit = max(max_profit, profit)

        return max_profit
```

---

## ⏱️ Complexity

* **Time:** `O(n)`
* **Space:** `O(1)`

---

## 🔑 Key Learning

* Keep track of the **minimum value seen so far**.
* At every element, calculate the profit if sold today.
* Store only the best profit instead of all profits.
* This is a classic **Running Minimum** pattern.

---

## ❌ Mistakes I Made

* Initially stored every profit in a dictionary, resulting in **O(n)** extra space.
* Used both minimum and maximum variables, making the solution more complex than necessary.
* Learned that only the **minimum price** and **maximum profit** are required.

---

## 🎯 Pattern Recognition

Use the **Running Minimum** pattern when a problem asks for:

* Maximum profit
* Maximum difference
* Best gain
* Maximum increase

Pattern:

```text
Running Minimum
        ↓
Current Profit
        ↓
Update Maximum Profit
```

---

## 📝 Revision Notes

* Buy at the **lowest price seen so far**.
* Sell at the **current price**.
* Never look ahead; use only past information.
* Formula to remember:

```python
min_price = min(min_price, price)
max_profit = max(max_profit, price - min_price)
```

---

## ✅ Status

* Solved Independently ✔️
* Optimal Solution ✔️
* Time: O(n)
* Space: O(1)

**Revision Schedule**

* 🔄 Revise after 1 day
* 🔄 Revise after 7 days
* 🔄 Revise after 30 days
