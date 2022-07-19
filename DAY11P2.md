# Maximum Depth of Binary Tree
---
- ## Question:
> Given the root of a binary tree, return its maximum depth.
> 
> A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/11/26/tmp-tree.jpg)
> Input: root = [3,9,20,null,null,15,7]
> 
> Output: 3
---
- ## Solution:
**Code :**
```java
class Solution {
    public int maxDepth(TreeNode root) {
        if(root==null)
            return 0;
        return 1+Math.max(maxDepth(root.left),maxDepth(root.right));
    }
}
