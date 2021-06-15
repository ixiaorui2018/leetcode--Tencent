# leetcode 136 只出现一次的数字

## edited by 王少锐

## c++

#### 简单的异或运算!

```cpp
class Solution {
public:
    int singleNumber(vector<int> &nums) {
        int ret = 0;
        int n = nums.size();
        for (int i = 0; i < n; i++) {
            ret = ret ^ nums[i];
        }
        return ret;
    }
};

```
