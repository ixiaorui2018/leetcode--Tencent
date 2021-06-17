# leetcode 008 字符串转换整数 (atoi)

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {string} s
 * @return {number}
 */
const myAtoi = function (s) {
    const re = new RegExp(/^(-|\+)?\d+/);
    let str = s.trim().match(re);
    let res = str ? Number(str[0]) : 0;
    return res >= 0 ? Math.min(res, 2 ** 31 - 1) : Math.max(res, -(2 ** 31));
};
```
