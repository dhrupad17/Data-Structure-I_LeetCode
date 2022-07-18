# Binary Tree Preorder Traversal
---
- ## Question:
> Given the root of a binary tree, return the preorder traversal of its nodes' values.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/09/15/inorder_1.jpg)
> Input: root = [1,null,2,3]
> 
> Output: [1,2,3]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> res =new ArrayList<Integer>();
        if(root!= null)
        {
            res.add(root.val);
            res.addAll(preorderTraversal(root.left));
            res.addAll(preorderTraversal(root.right));
        }
        return res;
    }
}
