# leetcode 122 买卖股票的最佳时机II
## edited by 王少锐
## c



```c
int maxProfit(int* prices, int pricesSize) {
    int i,j;
    int x=0,y=0;
    for(i=0;i<pricesSize-1;i++){
        for(j=i+1;j<pricesSize;j++){
            if(prices[j]-prices[i]>y)
                y=prices[j]-prices[i];
            if(prices[j]-prices[i]<=y||(j+1)>=pricesSize){
                i=j-1;
                x+=y;
                y=0;
                break;
            }
        }
    }
    return x;
}

```

