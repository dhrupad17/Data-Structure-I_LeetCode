# Remove Duplicates from Sorted List
---
- ## Question:
> Given the head of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/01/04/list1.jpg)
> Input: head = [1,1,2]
> 
> Output: [1,2]
---
- ## Solution:
**Code :**
```java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        if(head==null||head.next==null)
            return head;
        head.next=deleteDuplicates(head.next);
        if(head.val==head.next.val)
            return head.next;
        return head;
    }
}
