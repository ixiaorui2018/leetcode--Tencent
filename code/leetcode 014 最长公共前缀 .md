# leetcode 014 最长公共前缀

## edited by 王少锐

## c

```c
char *longestCommonPrefix(char **strs, int strsSize) {
    int x = strsSize;
    assert(strs);
    if (x == 1)
        return *(strs + 0);
    if (x == 0)
        return "";
    char *cur = *(strs + 0);
    char *head = *(strs + 1);
    char *tail = *(strs + 0);
    char *tmp = *(strs + 0);
    char *ret = NULL;
    while (*head == *tail) {
        head++;
        tail++;
    }
    for (int i = 2; i < x; i++) {
        cur = *(strs + i);
        head = *(strs + 0);
        while (*head == *cur) {
            head++;
            cur++;
        }
        if (head < tail)
            tail = head;
        if (tail == tmp)
            return "";
    }
    ret = (char *)malloc(sizeof(char) * (tail - tmp + 1));
    for (int i = 0; i < tail - tmp + 1; i++)
        *(ret + i) = *(tmp + i);
    *(ret + (tail - tmp)) = '\0';
    return ret;
}

```
