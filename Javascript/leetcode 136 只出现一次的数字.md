# leetcode 136 只出现一次的数字

## edited by 王少锐

## JavaScript

#### 简单的异或运算!

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const singleNumber = function (nums) {
    let res = 0;
    for (let i = 0; i < nums.length; i++) {
        res = res ^ nums[i];
    }
    return res;
};
```
