# Binary Tree Inorder Traversal

## Problem Statement
Given the root of a binary tree, return the inorder traversal of its nodes' values.

## Tags
![Tree](https://img.shields.io/badge/-Tree-blue) ![Depth-First Search](https://img.shields.io/badge/-Depth--First%20Search-green)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)

## Example
### Example 1
**Input**: 
```python
root = [1, null, 2, 3]
```
**Output**: 
```python
[1, 3, 2]
```

### Example 2
**Input**: 
```python
root = []
```
**Output**: 
```python
[]
```

### Example 3
**Input**: 
```python
root = [1]
```
**Output**: 
```python
[1]
```

## Constraints
- The number of nodes in the tree is in the range `[0, 100]`.
- `-100 <= Node.val <= 100`

## Solution
### Recursive Approach
```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def inorder_traversal(root):
    result = []
    def inorder(node):
        if node:
            inorder(node.left)
            result.append(node.val)
            inorder(node.right)
    inorder(root)
    return result
```

### Iterative Approach
```python
def inorder_traversal(root):
    result, stack = [], []
    current = root
    while current or stack:
        while current:
            stack.append(current)
            current = current.left
        current = stack.pop()
        result.append(current.val)
        current = current.right
    return result
```

## Explanation
### Recursive Approach
This solution uses a helper function to perform the inorder traversal recursively. It traverses the left subtree, processes the current node, and then traverses the right subtree.

### Iterative Approach
This solution uses a stack to simulate the recursive process. It iterates through the tree, pushing nodes onto the stack until it reaches the leftmost node. It then processes nodes by popping them from the stack and traversing their right subtrees.

## Test Cases
### Test Case 1
**Input**: 
```python
root = [1, 2, 3, null, null, 4, 5]
```
**Output**: 
```python
[2, 1, 4, 3, 5]
```

### Test Case 2
**Input**: 
```python
root = [1, null, 2, 3]
```
**Output**: 
```python
[1, 3, 2]
```

### Test Case 3
**Input**: 
```python
root = [1, 2]
```
**Output**: 
```python
[2, 1]
```
