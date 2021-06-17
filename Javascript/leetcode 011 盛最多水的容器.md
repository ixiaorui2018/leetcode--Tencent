# leetcode 011 盛最多水的容器

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} height
 * @return {number}
 */
const maxArea = function (height) {
    let left = 0,
        right = height.length - 1;
    let res = 0;
    while (left < right) {
        let minH = Math.min(height[left], height[right]);
        res = Math.max(minH * (right - left), res);
        height[left] < height[right] ? left++ : right--;
    }
    return res;
};
```
