# leetcode 011 盛最多水的容器
## edited by 王少锐
## C++


```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int left = 0;
        int right = height.size() - 1;
        int max = 0;
        while (right > left)
        {
            max = std::max(min(height[right], height[left]) * (right - left), max);
            if (height[right] > height[left])
                left++;
            else
                right--;
        }
        return max;
    }
};

```

