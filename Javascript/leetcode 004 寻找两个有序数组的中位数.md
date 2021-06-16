# leetcode 004 寻找两个有序数组的中位数

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number}
 */
var findMedianSortedArrays = function (nums1, nums2) {
    let m = nums1.length;
    let n = nums2.length;
    if (m > n) {
        let temp = nums1;
        nums1 = nums2;
        nums2 = temp;
        m = nums1.length;
        n = nums2.length;
    }
    let iMin = 0,
        iMax = m;
    while (iMin <= iMax) {
        let i = Math.floor((iMax + iMin) / 2);
        let j = Math.floor((m + n + 1) / 2) - i;
        if (j != 0 && i != m && nums2[j - 1] > nums1[i]) {
            iMin = i + 1;
        } else if (i != 0 && j != n && nums1[i - 1] > nums2[j]) {
            iMax = i - 1;
        } else {
            let maxLeft = 0;
            if (i == 0) {
                maxLeft = nums2[j - 1];
            } else if (j == 0) {
                maxLeft = nums1[i - 1];
            } else {
                maxLeft = Math.max(nums1[i - 1], nums2[j - 1]);
            }
            if ((m + n) % 2 == 1) {
                return maxLeft;
            }
            minRight = 0;
            if (i == m) {
                minRight = nums2[j];
            } else if (j == n) {
                minRight = nums1[i];
            } else {
                minRight = Math.min(nums2[j], nums1[i]);
            }
            return (maxLeft + minRight) / 2.0;
        }
    }
    return 0.0;
};
```
