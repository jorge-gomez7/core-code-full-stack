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

<br>
<hr>

## Tuesday

**1. Well of ideas**

For every good kata idea there seem to be quite a few bad ones!

In this kata you need to check the provided array (x) for good ideas 'good' and bad ideas 'bad'. If there are one or two good ideas, return 'Publish!', if there are more than 2 return 'I smell a series!'. If there are no good ideas, as is often the case, return 'Fail!'.

###### challenge 1 => [go to it!](https://www.codewars.com/kata/57f222ce69e09c3630000212 "Kata")

###### Solution

```javascript
function well(x) {
  const res = [];
  const ext = x.map((el, i) => {
    if (el == "good") res.push(el);
  });
  if (res.length > 2) return "I smell a series!";
  if (res.length == 1 || res.length == 2) return "Publish!";
  if (res.length == 0) return "Fail!";
}
```

<br>
<hr>

## Wednesday

**1. React Manage Events**

Write a react component that will display the current value of our counter.

The counter should start at 0.
There should be a button to add 1.
There should also be a button to subtract 1.
We want to be able to see the value of the counter - so it should be rendered! And for your buttons to work they will need an onClick prop.

In your render you should return:

The counter display element with an id of 'counter', containing the counter value.
An increment button with an id of 'increment'
A decrement button with an id of 'decrement'

###### challenge 1 => [go to it!](https://www.codewars.com/kata/5a8319f257c562ede8000037/ "Kata")

###### Solution

```javascript
import React from "react";

export class Counter extends React.Component {
  constructor(props) {
    // Your state
    super(props);
    this.state = { counter: 0 };
  }
  render() {
    return (
      <div>
        <h1 id="counter">{this.state.counter}</h1>

        <button
          id="decrement"
          onClick={() => this.setState({ counter: this.state.counter - 1 })}
          type="button"
        >
          Decrement
        </button>

        <button
          id="increment"
          onClick={() => this.setState({ counter: this.state.counter + 1 })}
          type="button"
        >
          Increment
        </button>
      </div>
    );
  }
}
```
