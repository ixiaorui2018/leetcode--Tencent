# leetcode 122 买卖股票的最佳时机 II

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
const maxProfit = function (prices) {
    let ans = 0;
    for (let i = 0; i < prices.length - 1; i++) {
        if (prices[i] < prices[i + 1]) {
            ans = ans + prices[i + 1] - prices[i];
        }
    }
    return ans;
};
```
