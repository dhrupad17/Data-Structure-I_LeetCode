# Validate Binary Search Tree
---
- ## Question:
> Given the root of a binary tree, determine if it is a valid binary search tree (BST).
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/12/01/tree1.jpg)
> Input: root = [2,1,3]
> 
> Output: true
---
- ## Solution:
**Code :**
```java
class Solution {
    TreeNode prev=null;
    public boolean isValidBST(TreeNode root) {
        if(root==null)
            return true;
        if(isValidBST(root.left)&&(prev==null|| root.val>prev.val))
        {
            prev=root;
            return isValidBST(root.right);
        }
        return false;
    }
}
