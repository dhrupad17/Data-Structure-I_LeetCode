# Valid Parentheses
---
- ## Question:
> Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
> 
> An input string is valid if:
> 
>- Open brackets must be closed by the same type of brackets.
>- Open brackets must be closed in the correct order.
---
- ## Example:
> Input: s = "()"
> 
> Output: true
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean isValid(String s) {
        Stack<Character> stack=new Stack<>();
        for(int i=0;i<s.length();i++)
        {
            char ch=s.charAt(i);
            if(ch=='(' || ch=='{'|| ch=='[')
                stack.push(ch);
            else if(stack.empty())
                return false;
            else if(ch==')'&& stack.pop()!='(')
                return false;
            else if(ch=='}'&& stack.pop()!='{')
                return false;
            else if(ch==']'&& stack.pop()!='[')
                return false;
        }
        if(stack.empty())
            return true;
        else
            return false;
    }
}
