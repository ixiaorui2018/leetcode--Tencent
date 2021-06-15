# leetcode 231 2 的幂

## edited by 王少锐

## c++

```cpp
class Solution {
public:
    bool isPowerOfTwo(int n) {
        return n > 0 && (int)pow(2, 30) % n == 0;
    }
};

```
