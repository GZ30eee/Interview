# Valid Anagram

## Problem Statement
Given two strings `s` and `t`, return true if `t` is an anagram of `s`, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

## Tags
![Hash Table](https://img.shields.io/badge/-Hash%20Table-green) ![String](https://img.shields.io/badge/-String-blue)

## Companies
![Google](https://img.shields.io/badge/-Google-red) ![Amazon](https://img.shields.io/badge/-Amazon-orange) ![Microsoft](https://img.shields.io/badge/-Microsoft-blue) ![Facebook](https://img.shields.io/badge/-Facebook-darkblue)


## Example
### Example 1
**Input**: 
```python
s = "anagram"
t = "nagaram"
```
**Output**: 
```python
True
```

### Example 2
**Input**: 
```python
s = "rat"
t = "car"
```
**Output**: 
```python
False
```

## Constraints
- `1 <= s.length, t.length <= 5 * 10^4`
- `s` and `t` consist of lowercase English letters.

## Solution
```python
def is_anagram(s, t):
    return sorted(s) == sorted(t)
```

## Explanation
This solution sorts both strings and compares them to check if they are anagrams. If the sorted versions of the strings are identical, then the original strings are anagrams of each other.

## Test Cases
### Test Case 1
**Input**: 
```python
s = "listen"
t = "silent"
```
**Output**: 
```python
True
```

### Test Case 2
**Input**: 
```python
s = "hello"
t = "billion"
```
**Output**: 
```python
False
```

### Test Case 3
**Input**: 
```python
s = "aabbcc"
t = "ccbbaa"
```
**Output**: 
```python
True
```
