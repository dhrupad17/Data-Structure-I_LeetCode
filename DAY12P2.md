# Path Sum
---
- ## Question:
> Given the root of a binary tree and an integer targetSum, return true if the tree has a root-to-leaf path such that adding up all the values along the path equals targetSum.
> 
> A leaf is a node with no children.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/01/18/pathsum1.jpg)
> Input: root = [5,4,8,11,null,13,4,7,2,null,null,null,1], targetSum = 22
> 
> Output: true
> 
> Explanation: The root-to-leaf path with the target sum is shown.
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if(root==null)
            return false;
        if(root.left==null && root.right==null && root.val==targetSum)
            return true;
        return hasPathSum(root.left,targetSum-root.val)|| hasPathSum(root.right,targetSum-root.val);
    }
}
