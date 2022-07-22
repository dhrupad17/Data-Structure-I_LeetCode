# Two Sum IV - Input is a BST
---
- ## Question:
> Given the root of a Binary Search Tree and a target number k, return true if there exist two elements in the BST such that their sum is equal to the given target.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/09/21/sum_tree_1.jpg)
> Input: root = [5,3,6,2,4,null,7], k = 9
> 
> Output: true
---
- ## Solution:
**Code :**
```java
class Solution {
    Set<Integer> ans=new HashSet<>();
    public boolean findTarget(TreeNode root, int k) {
        if(root==null)
            return false;
        if(ans.contains(k-root.val))
        {
            return true;
        }
        ans.add(root.val);
        return findTarget(root.left,k) || findTarget(root.right,k);
    }
}
