# Maximum Subarray

## Problem Statement
Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

## Tags
![Array](https://img.shields.io/badge/-Array-blue) ![Dynamic Programming](https://img.shields.io/badge/-Dynamic%20Programming-green)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)


## Example
### Example 1
**Input**: 
```python
nums = [-2,1,-3,4,-1,2,1,-5,4]
```
**Output**: 
```python
6
```
**Explanation**: 
The subarray `[4,-1,2,1]` has the largest sum `6`.

### Example 2
**Input**: 
```python
nums = [1]
```
**Output**: 
```python
1
```

### Example 3
**Input**: 
```python
nums = [5,4,-1,7,8]
```
**Output**: 
```python
23
```
**Explanation**: 
The subarray `[5,4,-1,7,8]` has the largest sum `23`.

## Constraints
- `1 <= nums.length <= 10^5`
- `-10^4 <= nums[i] <= 10^4`

## Solution
```python
def max_sub_array(nums):
    max_sum = current_sum = nums[0]
    for num in nums[1:]:
        current_sum = max(num, current_sum + num)
        max_sum = max(max_sum, current_sum)
    return max_sum
```

## Explanation
This solution uses Kadane's algorithm to find the maximum sum of a contiguous subarray in linear time. We maintain two variables: `current_sum` to keep track of the current subarray sum and `max_sum` to store the maximum sum encountered so far. As we iterate through the array, we update `current_sum` to be the maximum of the current number or the sum of `current_sum` and the current number. We then update `max_sum` to be the maximum of `max_sum` and `current_sum`.

## Test Cases
### Test Case 1
**Input**: 
```python
nums = [1, 2, 3, 4, 5]
```
**Output**: 
```python
15
```

### Test Case 2
**Input**: 
```python
nums = [-1, -2, -3, -4]
```
**Output**: 
```python
-1
```

### Test Case 3
**Input**: 
```python
nums = [3, -1, 2, -1]
```
**Output**: 
```python
4
```
