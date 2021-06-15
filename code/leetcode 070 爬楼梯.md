# leetcode 070 爬楼梯

## edited by 王少锐

## c

```c
//迭代法。
int climbStairs(int n) {
    int sum = 0, p2 = 2, p3 = 3;
    if (1 == n)
        return 1;
    if (2 == n)
        return 2;
    if (3 == n)
        return 3;
    while (n > 3) {
        sum = p2 + p3;
        p2 = p3;
        p3 = sum;
        n--;
    }
    return sum;
}

```
