# Binary Tree Inorder Traversal
---
- ## Question:
> Given the root of a binary tree, return the inorder traversal of its nodes' values.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/09/15/inorder_1.jpg)
> Input: root = [1,null,2,3]
> 
> Output: [1,3,2]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
    List<Integer> list = new ArrayList<Integer>();

    Stack<TreeNode> stack = new Stack<TreeNode>();
    TreeNode cur = root;

    while(cur!=null || !stack.empty()){
        while(cur!=null){
            stack.add(cur);
            cur = cur.left;
        }
        cur = stack.pop();
        list.add(cur.val);
        cur = cur.right;
    }

    return list;
}
}
