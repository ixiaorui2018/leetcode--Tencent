# leetcode 033 搜索旋转排序数组

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
const search = function (nums, target) {
    let left = 0,
        right = nums.length - 1;
    while (left <= right) {
        let mid = parseInt((left + right) / 2);
        if (nums[left] === target) return left;
        if (nums[right] === target) return right;
        if (nums[mid] === target) return mid;
        if (nums[left] < nums[mid]) {
            if (nums[left] < target && nums[mid] > target) {
                left = left + 1;
                right = mid - 1;
            } else {
                left = mid + 1;
                right = right - 1;
            }
        } else {
            if (nums[right] > target && nums[mid] < target) {
                left = mid + 1;
                right = right - 1;
            } else {
                left = left + 1;
                right = mid - 1;
            }
        }
    }
    return -1;
};
```
