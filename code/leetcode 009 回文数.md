# leetcode 009 回文数

## edited by 王少锐

## C++

```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        if (x < 0)
            return false;
        if (x < 10)
            return true;
        vector<int> t;
        while (x) {
            t.push_back(x % 10);
            x /= 10;
        }
        int l = t.size();
        if (l % 2 == 0) {
            for (int i = 0, j = l - 1; i < l / 2 && j >= l / 2; i++, j--) {
                if (t[i] != t[j])
                    return false;
            }
        }
        else {
            for (int i = 0, j = l - 1; i < l / 2 && j > l / 2; i++, j--) {
                if (t[i] != t[j])
                    return false;
            }
        }
        return true;
    }
};

```
