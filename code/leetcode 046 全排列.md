# leetcode 046 全排列
## edited by 王少锐
## c++


```cpp
class Solution {
public:
    vector<vector<int>>res;
    void f(vector<int>nums,int i,int j){
        if(i==j){
            res.push_back(nums);
            return;
        }
        for(int k=i;k<=j;k++){
            swap(nums[k],nums[i]);
            f(nums,i+1,j);
            swap(nums[k],nums[i]);
        }
    }
    vector<vector<int>> permute(vector<int>& nums) {
        f(nums,0,nums.size()-1);
        return res;
    }
};

```

