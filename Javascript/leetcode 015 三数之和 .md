# leetcode 015 三数之和

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} nums
 * @return {number[][]}
 */
/**
 * @param {number[]} nums
 * @return {number[][]}
 */
const threeSum = function (nums) {
    if (nums.length < 3) return []; // 数组小于三个元素，不符合题意;
    let len = nums.length;
    nums.sort((a, b) => a - b); // 按数字大小排序便于剪枝;
    console.log(nums);
    let result = [];
    let left; // 左指针;
    let right; // 右指针;
    let count;
    for (let i = 0; i < len - 2; i++) {
        if (nums[i] === nums[i - 1]) continue; // 去重剪枝;
        if (nums[i] + nums[i + 1] + nums[i + 2] > 0) break; // 若连续三个最小的数之和都大于0，后面不可能有解;
        if (nums[i] + nums[len - 2] + nums[len - 1] < 0) continue; // 若nums[i]加最大两个数都小于0，则nums[i]无解;
        left = i + 1;
        right = len - 1;
        while (left < right) {
            count = nums[i] + nums[left] + nums[right];
            if (count < 0) left++;
            // 如果和小于0，左指针右移;
            else if (count > 0) right--;
            // 如果和大于0，右指针左移;
            else {
                result.push([nums[i], nums[left], nums[right]]);
                while (nums[left] === nums[++left]) {}
                while (nums[right] === nums[--right]) {}
                // 这是因为a+b+c=0，若a,b不变，则c也不会变，但题目要求不能有重复解，所以左右指针都要移动;
            }
        }
    }
    return result;
};
```
