# leetcode 026 删除排序数组中的重复项

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const removeDuplicates = function (nums) {
    if (nums.length < 2) return nums.length;
    let length = 1;
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] != nums[length - 1]) {
            nums[length++] = nums[i];
        }
    }
    return length;
};
```
