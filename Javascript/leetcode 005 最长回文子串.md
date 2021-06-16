# leetcode 005 最长回文子串

## edited by 王少锐

## JavaScript

```javascript
const longestPalindrome = function (s) {
    let str = '@#';
    for (let i = 0; i < s.length; i++) {
        str += s[i] + '#';
    }
    str += '$';
    let child = [],
        mid = 0,
        right = 0,
        maxLen = 0,
        maxLenMid = 0;
    for (let i = 0; i < str.length; i++) {
        child[i] = i < right ? Math.min(child[2 * mid - i], right - i) : 1;
        while (str[i + child[i]] == str[i - child[i]]) {
            child[i]++;
        }
        if (right < child[i] + i) {
            right = child[i] + i;
            mid = i;
        }
        if (maxLen < child[i]) {
            maxLen = child[i];
            maxLenMid = mid;
        }
    }
    return s.substr((maxLenMid + 1 - maxLen) / 2, maxLen - 1);
};
```
