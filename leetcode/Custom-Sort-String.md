## Question

[Go to leetcode]('https://leetcode.com/explore/challenge/card/july-leetcoding-challenge-2021/609/week-2-july-8th-july-14th/3813/')

order and str are strings composed of lowercase letters. In order, no letter occurs more than once.

order was sorted in some custom order previously. We want to permute the characters of str so that they match the order that order was sorted. More specifically, if x occurs before y in order, then x should occur before y in the returned string.

Return any permutation of str (as a string) that satisfies this property.

Example 1:
```
Example:
Input: 
order = "cba"
str = "abcd"
Output: "cbad"
Explanation: 
"a", "b", "c" appear in order, so the order of "a", "b", "c" should be "c", "b", and "a". 
Since "d" does not appear in order, it can be at any position in the returned string. "dcba", "cdba", "cbda" are also valid outputs.
```

Constraints:

- order has length at most 26, and no character is repeated in order.
- str has length at most 200.
- order and str consist of lowercase letters only.

## Answer

```js
/**
 * @param {string} order
 * @param {string} str
 * @return {string}
 */
var customSortString = function(order, str) {
    let arr = [];
    const strArr = str.split('')
    for(let i = 0; i < order.length; i++){
      const a = strArr.filter(value => value === order[i]);
      arr.push(a.join(''));
    }
    
    const unique = strArr.filter(value => order.indexOf(value) === -1)
    return arr.concat(unique).join('')
};
```