# leetcode 033 搜索旋转排序数组

## edited by 王少锐

## c++

```cpp
class Solution {
public:
    int search(vector<int> &nums, int target, int left, int right) {
        while (left <= right) {
            int mid = (left + right) / 2;
            if (nums[mid] == target)
                return mid;
            else if (nums[mid] > target)
                right = mid - 1;
            else if (nums[mid] < target)
                left = mid + 1;
        }
        return -1;
    }
    int search(vector<int> &nums, int target) {
        int left = 0, right = nums.size() - 1;
        int mid = (left + right) / 2;
        while (left <= right) {
            if (nums[mid] >= nums[left]) {
                if (nums[mid] >= target && nums[left] <= target) {
                    return search(nums, target, left, mid);
                }
                else {
                    left = mid + 1;
                    mid = (left + right) / 2;
                }
            }
            else {
                if (nums[mid] <= target && nums[right] >= target) {
                    return search(nums, target, mid, right);
                }
                else {
                    right = mid - 1;
                    mid = (left + right) / 2;
                }
            }
        }
        return -1;
    }
};

```
