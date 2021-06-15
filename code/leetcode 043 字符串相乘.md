# leetcode 043 字符串相乘

## edited by 王少锐

## c++

```cpp
class Solution {
public:
    string multiply(string num1, string num2) {
        int l1 = num1.length(), l2 = num2.length();
        if (l1 == 0 || l2 == 0)
            return "";
        int a[300] = {0};
        for (int i = l1 - 1; i >= 0; --i) {
            for (int j = l2 - 1; j >= 0; --j) {
                int t = (num1[i] - '0') * (num2[j] - '0');
                t += a[i + j + 1];
                a[i + j] += t / 10;
                a[i + j + 1] = t % 10;
            }
        }
        string res = "";
        bool b = true;
        for (int i = 0; i < l1 + l2; i++) {
            if (i == l1 + l2 - 1 && a[i] == 0) {
                res += '0';
                break;
            }
            if (a[i] == 0 && b)
                continue;
            b = false;
            char c = a[i] += '0';
            res += c;
        }
        return res;
    }
};

```
