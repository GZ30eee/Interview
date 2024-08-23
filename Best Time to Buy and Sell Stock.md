# Best Time to Buy and Sell Stock

## Problem Statement
You are given an array `prices` where `prices[i]` is the price of a given stock on the `i`-th day. You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock. Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

## Tags
![Array](https://img.shields.io/badge/-Array-blue) ![Dynamic Programming](https://img.shields.io/badge/-Dynamic%20Programming-green)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)

## Example
### Example 1
**Input**: 
```python
prices = [7, 1, 5, 3, 6, 4]
```
**Output**: 
```python
5
```
**Explanation**: 
Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6 - 1 = 5.

### Example 2
**Input**: 
```python
prices = [7, 6, 4, 3, 1]
```
**Output**: 
```python
0
```
**Explanation**: 
In this case, no transactions are done and the max profit = 0.

## Constraints
- `1 <= prices.length <= 10^5`
- `0 <= prices[i] <= 10^4`

## Solution
```python
def max_profit(prices):
    min_price = float('inf')
    max_profit = 0
    for price in prices:
        if price < min_price:
            min_price = price
        elif price - min_price > max_profit:
            max_profit = price - min_price
    return max_profit
```

## Explanation
This solution iterates through the list of prices while keeping track of the minimum price encountered so far and the maximum profit that can be achieved. For each price, we update the minimum price if the current price is lower, and we calculate the potential profit if the current price is higher than the minimum price. The maximum profit is updated accordingly.

## Test Cases
### Test Case 1
**Input**: 
```python
prices = [1, 2, 3, 4, 5]
```
**Output**: 
```python
4
```

### Test Case 2
**Input**: 
```python
prices = [7, 1, 5, 3, 6, 4]
```
**Output**: 
```python
5
```

### Test Case 3
**Input**: 
```python
prices = [7, 6, 4, 3, 1]
```
**Output**: 
```python
0
```
