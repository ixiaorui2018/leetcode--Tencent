# leetcode 043 字符串相乘

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {string} num1
 * @param {string} num2
 * @return {string}
 */
const multiply = function (num1, num2) {
    let len1 = num1.length;
    let len2 = num2.length;
    let res = new Array(len1 + len2).fill(0);
    for (let i = len1 - 1; i >= 0; i--) {
        let n1 = +num1[i];
        for (let j = len2 - 1; j >= 0; j--) {
            let n2 = +num2[j];
            let multi = n1 * n2;
            res[i + j + 1] = res[i + j + 1] + multi;
            if (res[i + j + 1] >= 10) {
                res[i + j] = res[i + j] + parseInt(res[i + j + 1] / 10);
                res[i + j + 1] = res[i + j + 1] % 10;
            }
        }
    }
    while (res[0] === 0) {
        res.shift();
    }
    res = res.join('');
    return res.length ? res : 0;
};
```
