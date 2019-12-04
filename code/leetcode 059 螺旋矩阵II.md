# leetcode 059 螺旋矩阵II
## edited by 王少锐
## c++


```cpp
class Solution {
public:
    vector<vector<int>> generateMatrix(int n) {
        vector<vector<int>>res(n,vector<int>(n,0));
        int up=0,down=n-1,left=0,right=n-1;int x=1;
        while(true){
            for(int i=left;i<=right;i++) res[up][i]=x++;
            up++;if(up>down)break;
            for(int i=up;i<=down;i++)res[i][right]=x++;
            right--;if(right<left)break;
            for(int i=right;i>=left;i--)res[down][i]=x++;
            down--;if(up>down)break;
            for(int i=down;i>=up;i--)res[i][left]=x++;
            left++;if(right<left)break;
        }
        return res;
    }
};

```

