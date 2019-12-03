# leetcode 124 二叉树中的最大路径和
## edited by 王少锐
## Java


```java
class Solution {
    
    private int ret = Integer.MIN_VALUE;
    
    public int maxPathSum(TreeNode root) {
        getMax(root);
        return ret;
    }
    
    private int getMax(TreeNode r) {
        if(r == null) return 0;
        int left = Math.max(0, getMax(r.left)); 
        int right = Math.max(0, getMax(r.right));
        ret = Math.max(ret, r.val + left + right); 
        return Math.max(left, right) + r.val;
    }
}

```

