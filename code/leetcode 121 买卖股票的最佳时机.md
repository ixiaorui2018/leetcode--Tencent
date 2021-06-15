# leetcode 121 买卖股票的最佳时机

## edited by 王少锐

## c

```c
int maxProfit(int *prices, int pricesSize) {
    int max = 0;
    int i, min = prices[0];
    for (i = 0; i < pricesSize; i++) {
        if (min > prices[i])
            min = prices[i];
        else if (prices[i] - min > max)
            max = prices[i] - min;
    }
    return max;
}

```
