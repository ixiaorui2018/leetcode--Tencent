# leetcode 230 二叉搜索树中第 K 小的元素

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
    //统计子树个数;
    int f(TreeNode root) {
        if (root == null)
            return 0;
        return f(root.left) + f(root.right) + 1;
    }

    public int kthSmallest(TreeNode root, int k) {
        //统计左子树的子树个数，与k比较，判断结果在哪边!
        int leftN = f(root.left);
        if (leftN + 1 == k)
            return root.val;
        else if (k <= leftN)
            return kthSmallest(root.left, k);
        else
            return kthSmallest(root.right, k - leftN - 1);
    }
}

```
