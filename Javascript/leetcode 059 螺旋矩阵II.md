# leetcode 059 螺旋矩阵 II

## edited by 王少锐

## JavaScript

```javascript
const generateMatrix = function (n) {
    let res = new Array(n);
    for (let i = 0; i < n; i++) {
        res[i] = new Array(n);
    }
    let up = 0,
        down = n - 1,
        left = 0,
        right = n - 1,
        num = 1;
    while (num <= n * n) {
        for (let i = left; i <= right; i++) {
            res[up][i] = num;
            num++;
        }
        up++;
        for (let i = up; i <= down; i++) {
            res[i][right] = num;
            num++;
        }
        right--;
        for (let i = right; i >= left; i--) {
            res[down][i] = num;
            num++;
        }
        down--;
        for (let i = down; i >= up; i--) {
            res[i][left] = num;
            num++;
        }
        left++;
    }
    return res;
};
```
