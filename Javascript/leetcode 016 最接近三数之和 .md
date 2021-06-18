# leetcode 016 最接近三数之和

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
const threeSumClosest = function (nums, target) {
    nums.sort((a, b) => a - b);
    let gap = Infinity;
    let res = Infinity;
    for (let i = 0; i < nums.length - 2; i++) {
        let left = i + 1,
            right = nums.length - 1;
        while (left < right) {
            let temp = nums[i] + nums[left] + nums[right] - target;
            if (Math.abs(temp) < gap) {
                gap = Math.abs(temp);
                res = nums[i] + nums[left] + nums[right];
            }
            if (temp < 0) {
                left++;
            } else {
                right--;
            }
        }
    }
    return res;
};
```
