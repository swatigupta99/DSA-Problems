🧠 Problem: 182 Difficulty: Easy Link: [https://leetcode.com/problems/best-time-to-buy-and-sell-stock/]

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

 

Example 1:

Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
Example 2:

Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.
 

Constraints:

1 <= prices.length <= 105
0 <= prices[i] <= 104

✅ Solution (Python):

class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_price = float('inf')
        max_profit = 0

        for price in prices:
            if price < min_price:
                min_price = price
            elif price - min_price > max_profit:
                max_profit = price - min_price

        return max_profit

🧠 Explanation: 
-Initialize min_price to infinity to keep track of the lowest price seen so far.

-Initialize max_profit to 0 to store the maximum profit that can be achieved.

-Iterate through each day's price in the prices array:

-If the current price is less than min_price, update min_price (i.e., update the best day to buy).

-Else, calculate the profit by price - min_price, and update max_profit if this profit is greater than the current max_profit.

-After the loop, return max_profit, which will be the maximum profit obtainable from a single buy and sell operation.

Time: O(n) – Single pass through the array.
