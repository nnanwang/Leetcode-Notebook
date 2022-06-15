# 20. Valid Parentheses
Given a string ```s``` containing just the characters ```'('```, ```')'```, ```'{'```, ```'}'```, ```'['``` and ```']'```, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
 

#### Example 1:
```
Input: s = "()"
Output: true
```
#### Example 2:
```
Input: s = "()[]{}"
Output: true
```
#### Example 3:
```
Input: s = "(]"
Output: false
```

#### Constraints:

```1 <= s.length <= 104```
```s``` consists of parentheses only ```'()[]{}'```.
# Solution :dart:
![](https://img.shields.io/badge/language-Python-blue.svg)
```
class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        mapping = {")": "(", "}": "{", "]": "["}
        for x in s:
            if x in mapping:
            
                # Pop the top element in the stack if the stack is not empty.
                # Otherwise, assign '#' to top_element 
                
                top_element = stack.pop() if stack else '#'
                if mapping[x] != top_element:
                    return False
            else:
                stack.append(x)
        return not stack
  ```
