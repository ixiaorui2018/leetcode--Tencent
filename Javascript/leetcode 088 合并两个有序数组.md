# leetcode 88 合并两个有序数组

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
const merge = function (nums1, m, nums2, n) {
    let len1 = m - 1,
        len2 = n - 1,
        len = m + n - 1;
    while (len1 >= 0 && len2 >= 0) {
        nums1[len--] = nums1[len1] > nums2[len2] ? nums1[len1--] : nums2[len2--];
    }
    while (len2 >= 0) {
        nums1[len2] = nums2[len2--];
    }
    return nums1;
};

console.log(merge([0], 0, [1], 1));
```
