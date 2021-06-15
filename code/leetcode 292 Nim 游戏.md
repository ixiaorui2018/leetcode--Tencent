# leetcode 292 Nim 游戏

## edited by 王少锐

## c++

#### 巴什博奕，n%(m+1)!=0 时，先手总是会赢的!

```cpp
class Solution {
public:
    bool canWinNim(int n) {
        return n % 4;
    }
};

```
