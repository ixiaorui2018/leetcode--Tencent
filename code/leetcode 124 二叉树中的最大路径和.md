# leetcode 124 二叉树中的最大路径和

## edited by 王少锐

## c++/Java

#### 这道题有些争议，c++写法有一个测试样例，网页本地控制台执行是对的，提交出错!

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */

        /**
        对于任意一个节点, 如果最大和路径包含该节点, 那么只可能是两种情况:
        1. 其左右子树中所构成的和路径值较大的那个加上该节点的值后向父节点回溯构成最大路径;
        2. 左右子树都在最大路径中, 加上该节点的值构成了最终的最大路径;
        **/

int ret = -1000000000;
int getMax(TreeNode *root) {
    if (root == NULL)
        return 0;
    int left = max(0, getMax(root->left));
    int right = max(0, getMax(root->right));
    ret = max(ret, root->val + left + right);
    return max(left, right) + root->val;
}
class Solution {
public:
    int maxPathSum(TreeNode *root) {
        getMax(root);
        return ret;
    }
};

```

#### 基于上面的问题，写一个 Java 的写法!思路和 c++一致!

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
