# Merge Two Sorted Lists

## Problem Statement
Given the heads of two sorted linked lists `list1` and `list2`, merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists. Return the head of the merged linked list.

## Tags
![Linked List](https://img.shields.io/badge/-Linked%20List-blue)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)

## Example
### Example 1
**Input**: 
```python
list1 = [1, 2, 4]
list2 = [1, 3, 4]
```
**Output**: 
```python
[1, 1, 2, 3, 4, 4]
```

### Example 2
**Input**: 
```python
list1 = []
list2 = []
```
**Output**: 
```python
[]
```

### Example 3
**Input**: 
```python
list1 = []
list2 = [0]
```
**Output**: 
```python
[0]
```

## Constraints
- The number of nodes in both lists is in the range `[0, 50]`.
- `-100 <= Node.val <= 100`
- Both `list1` and `list2` are sorted in non-decreasing order.

## Solution
```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def merge_two_lists(l1, l2):
    dummy = ListNode()
    current = dummy
    while l1 and l2:
        if l1.val < l2.val:
            current.next = l1
            l1 = l1.next
        else:
            current.next = l2
            l2 = l2.next
        current = current.next
    current.next = l1 if l1 else l2
    return dummy.next
```

## Explanation
This solution iteratively merges two sorted linked lists by comparing the nodes and linking them in sorted order. We use a dummy node to simplify the merging process and a `current` pointer to build the new list. We compare the values of the nodes from both lists and attach the smaller node to the `current` pointer. We continue this process until we reach the end of one of the lists, then attach the remaining nodes from the other list.

## Test Cases
### Test Case 1
**Input**: 
```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
```
**Output**: 
```python
[1, 2, 3, 4, 5, 6]
```

### Test Case 2
**Input**: 
```python
list1 = [5, 10, 15]
list2 = [2, 3, 20]
```
**Output**: 
```python
[2, 3, 5, 10, 15, 20]
```

### Test Case 3
**Input**: 
```python
list1 = [1, 1]
list2 = [2, 4]
```
**Output**: 
```python
[1, 1, 2, 4]
```
