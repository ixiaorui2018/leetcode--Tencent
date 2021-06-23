# leetcode 054 螺旋矩阵

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[][]} matrix
 * @return {number[]}
 */
const spiralOrder = function (matrix) {
    let res = [];
    let up = 0,
        down = matrix.length - 1,
        left = 0,
        right = matrix[0].length - 1;
    while (true) {
        for (let i = left; i <= right; i++) res.push(matrix[up][i]);
        up++;
        if (up > down) break;
        for (let i = up; i <= down; i++) res.push(matrix[i][right]);
        right--;
        if (right < left) break;
        for (let i = right; i >= left; i--) res.push(matrix[down][i]);
        down--;
        if (up > down) break;
        for (let i = down; i >= up; i--) res.push(matrix[i][left]);
        left++;
        if (right < left) break;
    }
    return res;
};
```
