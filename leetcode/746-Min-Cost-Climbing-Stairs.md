## Question

[Go to leetcode]('https://leetcode.com/problems/min-cost-climbing-stairs/')

You are given an integer array cost where cost[i] is the cost of ith step on a staircase. Once you pay the cost, you can either climb one or two steps.

You can either start from the step with index 0, or the step with index 1.

Return the minimum cost to reach the top of the floor.

Example 1:
```
Input: cost = [10,15,20]
Output: 15
Explanation: Cheapest is: start on cost[1], pay that cost, and go to the top.
```

Example 2:
```
Input: cost = [1,100,1,1,1,100,1,1,100,1]
Output: 6
Explanation: Cheapest is: start on cost[0], and only step on 1s, skipping cost[3].
```

Constraints:

- 2 <= cost.length <= 1000
- 0 <= cost[i] <= 999

## Answer

```js
var minCostClimbingStairs = function(cost) {
	const dp = [cost[0], cost[1]];
  const leng = cost.length;
  
	for (let i = 2; i < leng; i++) {
		const num =  Math.min(dp[i - 1], dp[i - 2]) + cost[i];
		dp.push(num)
	}
  
	return Math.min(dp[leng - 1], dp[leng - 2]);
};
```