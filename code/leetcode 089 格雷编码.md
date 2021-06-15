# leetcode 089 格雷编码

## edited by 王少锐

## c++

```cpp
//异或操作，参考自评论区:Joy!
class Solution {
public:
    vector<int> grayCode(int n) {
        vector<int> v((1 << n), 0);
        for (int i = 1 << n; i--; v[i] = i ^ (i >> 1));
        return v;
    }
};

```
