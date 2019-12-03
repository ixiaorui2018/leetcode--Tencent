# leetcode 008 字符串转换整数 (atoi)
## edited by 王少锐
## C++


```cpp
//INT_MAX=2147483647
//INT_MIN=-2147483648

class Solution {
public:
    int myAtoi(string str) {
        int ret=0;
        int sign=1;
        int i=0;
        while(i<str.size()&&str[i]==' ')
            i++;
        if(i>=str.size())
            return 0;
        if(str[i]=='+'){
                if(i+1==str.size()||(str[i+1]>'9'||str[i+1]<'0'))
                    return 0;
                else
                    i++;
            }
            if(str[i]=='-'){
                if(i+1==str.size()||(str[i+1]>'9'||str[i+1]<'0'))
                    return 0;
                else{
                    sign=-sign;
                    i++;
                }
            }
        for(;i<str.size();i++){
            if(str[i]<'0'||str[i]>'9')
                break;
            if(ret>2147483647/10||(ret==2147483647/10&&(str[i]-'0')>2147483647%10))
                return sign==1?2147483647:-2147483648;
            ret=ret*10+(str[i]-'0');
        }
        return ret*sign;
    }
};

```

