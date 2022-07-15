# Ransom Note
---
- ## Question:
> Given two strings ransomNote and magazine, return true if ransomNote can be constructed by using the letters from magazine and false otherwise.
> 
> Each letter in magazine can only be used once in ransomNote.
---
- ## Example:
> Input: ransomNote = "a", magazine = "b"
> 
> Output: false
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean canConstruct(String r, String m) {
        int[] freq=new int[26];
        for(int i=0;i<m.length();i++)
        {
            freq[m.charAt(i)-'a']++;
        }
        for(int i=0;i<r.length();i++)
        {
            if(--freq[r.charAt(i)-'a']<0)
                return false;
        }
        return true;
    }
}
