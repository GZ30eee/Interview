# Reverse Linked List

## Problem Statement
Given the head of a singly linked list, reverse the list, and return the reversed list.

## Tags
![Linked List](https://img.shields.io/badge/-Linked%20List-blue)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)

## Example
### Example 1
**Input**: 
```python
head = [1, 2, 3, 4, 5]
```
**Output**: 
```python
[5, 4, 3, 2, 1]
```

### Example 2
**Input**: 
```python
head = [1, 2]
```
**Output**: 
```python
[2, 1]
```

### Example 3
**Input**: 
```python
head = []
```
**Output**: 
```python
[]
```

## Constraints
- The number of nodes in the list is in the range `[0, 5000]`.
- `-5000 <= Node.val <= 5000`

## Solution
```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def reverse_list(head):
    prev = None
    current = head
    while current:
        next_node = current.next
        current.next = prev
        prev = current
        current = next_node
    return prev
```

## Explanation
This solution iteratively reverses the linked list by changing the `next` pointers of each node. We use three pointers: `prev` to keep track of the previous node, `current` to keep track of the current node, and `next_node` to keep track of the next node. We update the `next` pointer of the current node to point to the previous node and move the pointers one step forward until we reach the end of the list.

## Test Cases
### Test Case 1
**Input**: 
```python
head = [1, 2, 3, 4, 5]
```
**Output**: 
```python
[5, 4, 3, 2, 1]
```

### Test Case 2
**Input**: 
```python
head = [1, 2, 3, 4]
```
**Output**: 
```python
[4, 3, 2, 1]
```

### Test Case 3
**Input**: 
```python
head = [1]
```
**Output**: 
```python
[1]
```
