# Two Sum

## Problem Statement
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

## Tags
![Array](https://img.shields.io/badge/-Array-blue) ![Hash Table](https://img.shields.io/badge/-Hash%20Table-green)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)

## Example
### Example 1
**Input**: 
```python
nums = [2, 7, 11, 15]
target = 9
```
**Output**: 
```python
[0, 1]
```
**Explanation**: 
Because `nums[0] + nums[1] == 9`, we return `[0, 1]`.

### Example 2
**Input**: 
```python
nums = [3, 2, 4]
target = 6
```
**Output**: 
```python
[1, 2]
```

### Example 3
**Input**: 
```python
nums = [3, 3]
target = 6
```
**Output**: 
```python
[0, 1]
```

## Constraints
- `2 <= nums.length <= 10^4`
- `-10^9 <= nums[i] <= 10^9`
- `-10^9 <= target <= 10^9`
- Only one valid answer exists.

## Solution
```python
def two_sum(nums, target):
    num_map = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        num_map[num] = i
```

## Explanation
This solution uses a hash table to store the indices of the numbers as we iterate through the array. For each number, we check if its complement (target - num) exists in the hash table. If it does, we return the indices of the current number and its complement.

## Test Cases
### Test Case 1
**Input**: 
```python
nums = [1, 2, 3, 4, 5]
target = 9
```
**Output**: 
```python
[3, 4]
```

### Test Case 2
**Input**: 
```python
nums = [0, -1, 2, -3, 1]
target = -2
```
**Output**: 
```python
[1, 3]
```

### Test Case 3
**Input**: 
```python
nums = [1, 1, 1, 1, 1]
target = 2
```
**Output**: 
```python
[0, 1]
```
