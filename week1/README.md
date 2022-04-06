## Week 1

### Tuesday

###### challenge 1 => [go to it!](https://www.codewars.com/kata/5866fc43395d9138a7000006 "Kata")

###### Solution

```javascript
function ensureQuestion(s) {
   if(s.substr(-1) == '?') return s;

  return s.concat('?');
}
```

###### challenge 2 => [go to it!](https://www.codewars.com/kata/51c8991dee245d7ddf00000e "Kata")

###### Solution

```javascript
function reverseWords(str){
  return str.split(' ').reverse().join(' ');
}
```
