# leetcode 009 回文数

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
const isPalindrome = function (x) {
    if (x < 0) return false;
    x = x + '';
    let xt = x.split('').reverse().join('');
    return xt === x;
};
```
