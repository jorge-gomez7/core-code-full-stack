# Week 2

## Monday

**1. Palindrome strings**

A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This includes capital letters, punctuation, and word dividers.
Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.
**Example:**

```
isPalindrome("anna")   ==> true
isPalindrome("walter") ==> false
isPalindrome(12321)    ==> true
isPalindrome(123456)   ==> false
```

###### challenge 1 => [go to it!](https://www.codewars.com/kata/57a5015d72292ddeb8000b31 "Kata")

###### Solution

```javascript
function isPalindrome(line) {
  return line.toString().split("").reverse().join("") == line;
}
```