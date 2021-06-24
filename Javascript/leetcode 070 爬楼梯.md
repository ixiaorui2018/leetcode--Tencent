# leetcode 070 爬楼梯

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number} n
 * @return {number}
 */
const climbStairs = function (n) {
    if (n === 1) return 1;
    if (n === 2) return 2;
    let arr = new Array(n).fill(1);
    arr[1] = 2;
    for (let i = 2; i < n; i++) arr[i] = arr[i - 1] + arr[i - 2];
    return arr[n - 1];
};
```
