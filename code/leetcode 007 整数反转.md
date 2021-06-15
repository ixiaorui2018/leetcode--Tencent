# leetcode 007 整数反转

## edited by 王少锐

## C

```c
int reverse(int x) {
    int num = 0;
    while (x != 0) {
        int t = num;
        num = num * 10 + x % 10;
        //检验溢出；
        if ((num - x % 10) != t)
            if (num % 10 != x % 10)
                return 0;
        x /= 10;
    }
    return num;
}

```
