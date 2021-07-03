# leetcode 089 格雷编码

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number} n
 * @return {number[]}
 */
const grayCode = function (n) {
    if (n === 0) return [0];
    const codes = grayCode(--n);
    return [...codes, ...codes.map((x) => (1 << n) | x).reverse()];
};
```
