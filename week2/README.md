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

<br>
<hr>

## Thursday

**1. Santa wish list form in ReactJS**

Santa wants to simplify his life and offer children the possiblity to enter their wishlist via an online form.

The form should be a React component and should contain:

an input field for the child's name (with id 'name')
a text area to describe the wish (id: 'wish')
a drop-down indicating the priority of the wish, from 1 to 5 - default is 1 (id: 'priority')
the keys in the state to store the corresponding values should be named the same as the element's id
an onSubmit action calling the function handleSubmit
a function called handleSubmit, which
calls send (a function that is already provided as part of the injected properties props)
passes the current state as a parameter to send
calls event.preventDefault
it should be a controlled component (i.e. using onChange to bind input to the component's state)

###### challenge 1 => [go to it!](https://www.codewars.com/kata/5a9ecd89fd5777e0790001ea/ "Kata")

###### Solution

```javascript
const React = require("react");

class WishlistForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "",
      wish: "",
      priority: 1,
    };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    const target = event.target;
    const value = target.value;
    const id = target.id == "select" ? "priority" : target.id;
    console.log(target);
    this.setState({
      [id]: value,
    });
    this.setState({ name: value });
  }

  handleSubmit(event) {
    event.preventDefault();
    this.props.send(this.state);
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <input
          name="name"
          id="name"
          type="text"
          value={this.state.name}
          onChange={this.handleChange}
        />
        <textarea
          name="wish"
          id="wish"
          value={this.state.wish}
          onChange={this.handleChange}
        />
        <select
          name="priority"
          id="priority"
          value={this.state.priority}
          onChange={this.handleChange}
        >
          <option value="1" default>
            {" "}
            1{" "}
          </option>
          <option value="2"> 2 </option>
          <option value="3"> 3 </option>
          <option value="4"> 4 </option>
          <option value="5"> 5 </option>
        </select>
      </form>
    );
  }
}
```
