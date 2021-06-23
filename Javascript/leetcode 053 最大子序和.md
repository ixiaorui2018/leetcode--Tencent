# leetcode 053 最大子序和

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const maxSubArray = function (nums) {
    let res = -Infinity;
    let temp = 0;
    for (let i = 0; i < nums.length; i++) {
        temp = temp < 0 ? nums[i] : temp + nums[i];
        res = res < temp ? temp : res;
    }
    return res;
};
```
