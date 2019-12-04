# leetcode 235 二叉搜索树的最近公共祖先
## edited by 王少锐
## Java



```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if (p.val==root.val){
            return p;
        } 
        if (q.val==root.val){
            return q;
        }
        if (p.val > root.val && q.val > root.val) {
            return lowestCommonAncestor(root.right,p,q);
        }else if (p.val < root.val && q.val < root.val) {
            return lowestCommonAncestor(root.left,p,q);
        }else{
            return root;
        }
    }
}

```

