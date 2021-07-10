# leetcode 121 买卖股票的最佳时机

## edited by 王少锐

## JavaScript

```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
const maxProfit = function (prices) {
    let leftMin = Infinity;
    let temp = new Array(prices.length).fill(0);
    for (let i = 0; i < prices.length; i++) {
        if (leftMin > prices[i]) {
            leftMin = prices[i];
        } else {
            temp[i] = prices[i] - leftMin;
        }
    }
    let ans = -1;
    for (let i = 0; i < temp.length; i++) {
        if (ans < temp[i]) {
            ans = temp[i];
        }
    }
    return ans;
};
```
