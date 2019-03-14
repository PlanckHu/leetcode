## Valid Parentheses

[题目](https://leetcode.com/problems/valid-parentheses/)

## 题目描述

给予一个填入了 **'('** , **')'**, **'{'** , **'}'** , **'['** and **']'** 的字符串，检验该字符串的括号是否闭合且是否正确匹配闭合顺序

## 约定

* 认为空字符串为valid

## 示例
Example 1:
```
Input: "()"
Output: true
```
Example 2:
```
Input: "()[]{}"
Output: true
```
Example 3:
```
Input: "(]"
Output: false
```
Example 4:
```
Input: "([)]"
Output: false
```
Example 5:
```
Input: "{[]}"
Output: true
```
## 解答

用入栈出栈的方法
``` java
// JAVA 
class Solution {
    public boolean isValid(String s) {
        List<Character> stack = new ArrayList<>();
        if (s.length() == 0) return true;
        for (int i = 0; i < s.length(); i++) {
            if (stack.isEmpty())
                stack.add(s.charAt(i));
            else {
                if (match(stack.get(stack.size() - 1), s.charAt(i))) {
                    stack.remove(stack.size() - 1);
                }else {
                    stack.add(s.charAt(i));
                }
            }
        }
        if (stack.size() != 0) return false;
        return true;
    }

    private boolean match(char c1, char c2) {
        if ((c1 == '(' && c2 == ')')
                || (c1 == '[' && c2 == ']')
                || (c1 == '{' && c2 == '}'))
            return true;
        else return false;
    }
}
```
