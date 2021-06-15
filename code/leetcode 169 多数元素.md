# leetcode 169 多数元素

## edited by 王少锐

## c++

```cpp
class Solution {
public:
    int majorityElement(vector<int> &nums) {
        int count = 1;
        int flag = nums[0];
        for (int i = 1; i < nums.size(); i++) {
            if (flag == nums[i])
                count++;
            else {
                count--;
                if (count == 0) {
                    flag = nums[i + 1];
                }
            }
        }
        return flag;
    }
};

```
