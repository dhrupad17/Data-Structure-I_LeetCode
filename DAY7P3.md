# Remove Linked List Elements
---
- ## Question:
> Given the head of a linked list and an integer val, remove all the nodes of the linked list that has Node.val == val, and return the new head.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/03/06/removelinked-list.jpg)
> Input: head = [1,2,6,3,4,5,6], val = 6
> 
> Output: [1,2,3,4,5]
---
- ## Solution:
**Code :**
```java
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        if(head==null)
            return null;
        head.next=removeElements(head.next,val);
        if(head.val==val)
            return head.next;
        return head;
    }
}
