# leetcode 020 有效的括号

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
const isValid = function (s) {
    if (s.length === 0) return true;
    let arr = [];
    const map = new Map();
    map.set('(', ')');
    map.set('{', '}');
    map.set('[', ']');
    let len = s.length;
    for (let i = 0; i < len; i++) {
        const c = s[i];
        if (map.has(c)) arr.push(c);
        else {
            const t = arr[arr.length - 1];
            if (map.get(t) === c) arr.pop();
            else return false;
        }
    }
    return arr.length === 0;
};
```
