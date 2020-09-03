# 1351. Count Negative Numbers in a Sorted Matrix

[Go to leetcode](https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/)

Given a m * n matrix grid which is sorted in non-increasing order both row-wise and column-wise. 

Return the number of negative numbers in grid.

Example 1:

```
Input: grid = [[4,3,2,-1],[3,2,1,-1],[1,1,-1,-2],[-1,-1,-2,-3]]
Output: 8
Explanation: There are 8 negatives number in the matrix.
```

Example 2:

```
Input: grid = [[3,2],[1,0]]
Output: 0
```

Example 3:

```
Input: grid = [[1,-1],[-1,-1]]
Output: 3
```

Example 4:
```
Input: grid = [[-1]]
Output: 1
```
 
Note:

- m == grid.length
- n == grid[i].length
- 1 <= m, n <= 100
- -100 <= grid[i][j] <= 100

## Answer

```js
/**
 * @param {number[][]} grid
 * @return {number}
 */
var countNegatives = function(grid) {
   let res = 0;
   const plusNumber = (arr) => {
     for(let i = 0; i < arr.length; i++){
       if(Math.sign(arr[i]) === -1) res++;
     }
   };
  
   for(let i = 0; i < grid.length; i++){
     plusNumber(grid[i]);
   }
  
  return res;
};
```