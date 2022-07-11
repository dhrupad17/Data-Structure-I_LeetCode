# Best Time to Buy and Sell Stock
---
- ## Question:
> You are given an array prices where prices[i] is the price of a given stock on the ith day.
> 
> You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
> 
> Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.
---
- ## Example:
> Input: prices = [7,1,5,3,6,4]
> 
> Output: 5
> 
> Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
---
- ## Solution:
**Code :**
```java
class Solution {
    public int maxProfit(int[] p) {
        int max=0;
        int min=p[0];
        for(int i=1;i<p.length;i++)
        {
            if(min<p[i])
            {
                max=Math.max(p[i]-min,max);
            }
            else
            {
                min=p[i];
            }
        }
        return max;
    }
}
