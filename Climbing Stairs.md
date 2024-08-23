# Climbing Stairs

## Problem Statement
You are climbing a staircase. It takes `n` steps to reach the top. Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

## Tags
![Dynamic Programming](https://img.shields.io/badge/-Dynamic%20Programming-green)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)

## Example
### Example 1
**Input**: 
```python
n = 2
```
**Output**: 
```python
2
```
**Explanation**: 
There are two ways to climb to the top:
1. 1 step + 1 step
2. 2 steps

### Example 2
**Input**: 
```python
n = 3
```
**Output**: 
```python
3
```
**Explanation**: 
There are three ways to climb to the top:
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

## Constraints
- `1 <= n <= 45`

## Solution
```python
def climb_stairs(n):
    if n == 1:
        return 1
    dp = [0] * (n + 1)
    dp[1], dp[2] = 1, 2
    for i in range(3, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]
    return dp[n]
```

## Explanation
This solution uses dynamic programming to find the number of distinct ways to climb to the top. We use an array `dp` where `dp[i]` represents the number of ways to reach the `i`-th step. The relation `dp[i] = dp[i - 1] + dp[i - 2]` is derived from the fact that to reach the `i`-th step, one can either come from the `(i-1)`-th step or the `(i-2)`-th step.

## Test Cases
### Test Case 1
**Input**: 
```python
n = 4
```
**Output**: 
```python
5
```

### Test Case 2
**Input**: 
```python
n = 5
```
**Output**: 
```python
8
```

### Test Case 3
**Input**: 
```python
n = 6
```
**Output**: 
```python
13
```
