# Valid Parentheses

## Problem Statement
Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

## Tags
![Stack](https://img.shields.io/badge/-Stack-blue) ![String](https://img.shields.io/badge/-String-green)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)

An input string is valid if:
1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

## Example
### Example 1
**Input**: 
```python
s = "()"
```
**Output**: 
```python
True
```

### Example 2
**Input**: 
```python
s = "()[]{}"
```
**Output**: 
```python
True
```

### Example 3
**Input**: 
```python
s = "(]"
```
**Output**: 
```python
False
```

## Constraints
- `1 <= s.length <= 10^4`
- `s` consists of parentheses only '()[]{}'.

## Solution
```python
def is_valid(s):
    stack = []
    mapping = {')': '(', '}': '{', ']': '['}
    for char in s:
        if char in mapping:
            top_element = stack.pop() if stack else '#'
            if mapping[char] != top_element:
                return False
        else:
            stack.append(char)
    return not stack
```

## Explanation
This solution uses a stack to keep track of opening brackets and ensures they are closed in the correct order. For each character in the string, if it is a closing bracket, we check if it matches the top of the stack. If it does, we pop the stack; otherwise, the string is invalid. If we encounter an opening bracket, we push it onto the stack. The string is valid if the stack is empty at the end.

## Test Cases
### Test Case 1
**Input**: 
```python
s = "([{}])"
```
**Output**: 
```python
True
```

### Test Case 2
**Input**: 
```python
s = "([)]"
```
**Output**: 
```python
False
```

### Test Case 3
**Input**: 
```python
s = "{[]}"
```
**Output**: 
```python
True
```
