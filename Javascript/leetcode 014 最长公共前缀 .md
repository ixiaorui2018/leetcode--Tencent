# leetcode 014 最长公共前缀

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {string[]} strs
 * @return {string}
 */
const longestCommonPrefix = function (strs) {
    let res = '';
    let breakFlag = false;
    for (let i = 0; i < strs[0].length; i++) {
        for (const str of strs) {
            if (str[i] != strs[0][i]) {
                breakFlag = true;
                break;
            }
        }
        if (breakFlag) break;
        res += strs[0][i];
    }
    return res;
};
```
