# 557. Reverse Words in a String III

[Go to leetcode](https://leetcode.com/problems/reverse-words-in-a-string-iii/)

Given a string, you need to reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

Example 1:

```
Input: "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
```
 
Note:

- In the string, each word is separated by single space and there will not be any extra space in the string.

## Answer

```js
/**
 * @param {string} s
 * @return {string}
 */
var reverseWords = function(s) {
    const splitStr = s.split(' ');
    return splitStr.map((str)=>{
        return str.split('').reverse().join('')
    }).join(' ');
};
```