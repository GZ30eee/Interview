# Merge Intervals

## Problem Statement
Given an array of intervals where `intervals[i] = [starti, endi]`, merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.

## Tags
![Array](https://img.shields.io/badge/-Array-blue) ![Sorting](https://img.shields.io/badge/-Sorting-green)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)


## Example
### Example 1
**Input**: 
```python
intervals = [[1,3],[2,6],[8,10],[15,18]]
```
**Output**: 
```python
[[1,6],[8,10],[15,18]]
```
**Explanation**: 
Since intervals `[1,3]` and `[2,6]` overlap, merge them into `[1,6]`.

### Example 2
**Input**: 
```python
intervals = [[1,4],[4,5]]
```
**Output**: 
```python
[[1,5]]
```
**Explanation**: 
Intervals `[1,4]` and `[4,5]` are considered overlapping.

## Constraints
- `1 <= intervals.length <= 10^4`
- `intervals[i].length == 2`
- `0 <= starti <= endi <= 10^4`

## Solution
```python
def merge(intervals):
    intervals.sort(key=lambda x: x[0])
    merged = []
    for interval in intervals:
        if not merged or merged[-1][1] < interval[0]:
            merged.append(interval)
        else:
            merged[-1][1] = max(merged[-1][1], interval[1])
    return merged
```

## Explanation
This solution sorts the intervals by their start times and then merges overlapping intervals by comparing the end time of the last added interval with the start time of the current interval.

## Test Cases
### Test Case 1
**Input**: 
```python
intervals = [[1,3],[2,4],[5,7],[6,8]]
```
**Output**: 
```python
[[1,4],[5,8]]
```

### Test Case 2
**Input**: 
```python
intervals = [[1,4],[0,4]]
```
**Output**: 
```python
[[0,4]]
```

### Test Case 3
**Input**: 
```python
intervals = [[1,4],[2,3]]
```
**Output**: 
```python
[[1,4]]
```
