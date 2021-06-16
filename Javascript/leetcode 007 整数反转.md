# leetcode 007 整数反转

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number} x
 * @return {number}
 */
const reverse = function (x) {
    let isNegative = false;
    if (x < 0) {
        x = -x;
        isNegative = true;
    }
    x = x + '';
    x = x.split('').reverse().join('');
    if (isNegative) {
        x = '-' + x;
    }
    x = +x;
    if (x > 2 ** 31 - 1 || x < -(2 ** 31)) {
        return 0;
    }
    return x;
};

```
