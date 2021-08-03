# leetcode 124 二叉树中的最大路径和

## edited by 王少锐

## JavaScript

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number}
 */
const maxPathSum = function (root) {
    let res = -Infinity;
    const getMax = (root) => {
        if (!root) return 0;
        let left = Math.max(0, getMax(root.left));
        let right = Math.max(0, getMax(root.right));
        res = Math.max(res, root.val + left + right);
        return Math.max(left, right) + root.val;
    };
    getMax(root);
    return res;
};
```
