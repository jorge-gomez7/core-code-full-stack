# Week 1

## Tuesday

**1. Ensure question**

Given a string, write a function that returns the string with a question mark ("?") appends to the end, unless the original string ends with a question mark, in which case, returns the original string.

**Example:**

```
"Yes" --> "Yes?"
"No?" --> "No?"
```

###### challenge 1 => [go to it!](https://www.codewars.com/kata/5866fc43395d9138a7000006 "Kata")

###### Solution

```javascript
function ensureQuestion(s) {
  if (s.substr(-1) == "?") return s;

  return s.concat("?");
}
```

<br>
<hr>

**2. Reversed Words**

Complete the solution so that it reverses all of the words within the string passed in.

**Example:**

```
"The greatest victory is that which requires no battle" --> "battle no requires which that is victory greatest The"
```

###### challenge 2 => [go to it!](https://www.codewars.com/kata/51c8991dee245d7ddf00000e "Kata")

###### Solution

```javascript
function reverseWords(str) {
  return str.split(" ").reverse().join(" ");
}
```

<br>
<hr>

## Wednesday

Given an array of integers your solution should find the smallest integer. You can assume, for the purpose of this kata, that the supplied array
will not be empty.

**Example:**

```
Given [34, 15, 88, 2] your solution will return 2
Given [34, -345, -1, 100] your solution will return -345
```

###### challenge 1 => [go to it!](https://www.codewars.com/kata/55a2d7ebe362935a210000b2 "Kata")

###### Solution

```javascript
class SmallestIntegerFinder {
  findSmallestInt(args) {
    return args.sort((a, b) => a - b)[0];
  }
}
```
