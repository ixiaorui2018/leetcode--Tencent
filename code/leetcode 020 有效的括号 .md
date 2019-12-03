# leetcode 020 有效的括号
## edited by 王少锐
## c


```c
bool isValid(char* s) {
    char a[10240];
    int i=0,j=-1;
    while(s[i]!='\0'){
        if(s[i]=='(')
            a[++j]='(';
        else if(s[i]=='[')
            a[++j]='[';
        else if(s[i]=='{')
            a[++j]='{';
        else if(s[i]==')'){
            if(j==-1||a[j]!='(')
                j=-2;
            else
                j--;
        }
        else if(s[i]==']'){
            if(j==-1||a[j]!='[')
                j=-2;
            else
                j--;
        }
        else if(s[i]=='}'){
            if(j==-1||a[j]!='{')
                j=-2;
            else
                j--;
        }
        if(j==-2)
            break;
        i++;
    }
    if(j!=-1)
        return false;
    else
        return true;
}

```

