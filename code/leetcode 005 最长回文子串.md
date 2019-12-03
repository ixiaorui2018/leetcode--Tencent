# leetcode 005 最长回文子串
## edited by 王少锐
## C


```c
char* longestPalindrome(char* s) {
    int len=strlen(s);
    if(len<=1)
        return s;
    int start=0,maxlen=0;
    for(int i=1;i<len;i++){
        int low=i-1;
        int high=i;
        while(low>=0&&high<len&&s[low]==s[high]){
            low--;
            high++;
        }
        if(high-low-1>maxlen){
            maxlen=high-low-1;
            start=low+1;
        }
        low=i-1;high=i+1;
        while(low>=0&&high<len&&s[low]==s[high]){
            low--;
            high++;
        }
        if(high-low-1>maxlen){
            maxlen=high-low-1;
            start=low+1;
        }
    }
    char *str=(char*)malloc(sizeof(int)*(maxlen*2));
    int i=0;
    for(;i<maxlen;i++)
        str[i]=s[start++];
    str[i]='\0';
    return str;
}

```

