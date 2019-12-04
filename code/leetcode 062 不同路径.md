# leetcode 062 不同路径
## edited by 王少锐
## c++


```cpp
class Solution {
public:
    int uniquePaths(int m, int n) {
        if(n<=1 || m<=1) return 1;
        int dp[1000] = {1};
        fill(dp,dp+m,1);
        while (--n>0){
            for (int i = 1; i < m; ++i) {
                dp[i] = dp[i]+dp[i-1];
            }
        }
        return dp[m-1];
    }
};

```

