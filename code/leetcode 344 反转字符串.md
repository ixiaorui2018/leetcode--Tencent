# leetcode 344 反转字符串
## edited by 王少锐
## c++



```cpp
class Solution {
public:
    void reverseString(vector<char>& s) {
        int i=0,j=s.size()-1;
        while(i<j){
            char c;
            c=s[i];
            s[i]=s[j];
            s[j]=c;
            i++;
            j--;
        }
    }
};

```

