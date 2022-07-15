# Valid Anagram
---
- ## Question:
> Given two strings s and t, return true if t is an anagram of s, and false otherwise.
> 
> An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.
---
- ## Example:
> Input: s = "anagram", t = "nagaram"
> 
> Output: true
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean isAnagram(String s, String t) {
        int [] alpha=new int[26];
        for(int i=0;i<s.length();i++)
        {
            alpha[s.charAt(i)-'a']++;
        }
        for(int i=0;i<t.length();i++)
        {
            alpha[t.charAt(i)-'a']--;
        }
        for(int i: alpha)
        {
            if(i!=0)
                return false;
        }
        return true;
    }
}
