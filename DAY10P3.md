# Binary Tree Postorder Traversal
---
- ## Question:
> Given the root of a binary tree, return the postorder traversal of its nodes' values.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/08/28/pre1.jpg)
> Input: root = [1,null,2,3]
> 
> Output: [3,2,1]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> res =new ArrayList<Integer>();
        if(root!= null)
        {
           
            res.addAll(postorderTraversal(root.left));
            res.addAll(postorderTraversal(root.right));
            res.add(root.val);
        }
        return res;
    }
}
