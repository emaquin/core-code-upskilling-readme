# core-code-upskilling-readme

# Week 1

## Ensure Question

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ensure Question</title>
    
</head>
<body>

<p id="demo"></p>

<script>

    let s = "Guatemala";
              
    function ensureQuestion (s) {
      return s.endsWith("?") ? s : s + "?";       
    } 
    
    document.getElementById("demo").innerHTML = ensureQuestion(s);

</script>

</body>
</html>

```

## Reversed Words

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reversed Words</title>
</head>
<body>

<p id="demo"></p>    
    
<script>

    let str = "Guatemala feliz que tus aras";

    function reversedWords(str) {
            return str
                .split(" ")
                .reverse()
                .join(" ");
        }

    document.getElementById("demo").innerHTML = reversedWords(str);

</script>    
    
</body>
</html>

```
## Smallest Integer in Array 

```
const arr = [14, 58, 20, 77, 66, 82, 42, 67, 42, 4]
            const min = Math.min(...arr)
            console.log(min)

```
## Odd or Even

```
const arr = [5, 1, 8, 4, 6, 9];
            const assignSum = (arr = []) => {
                const sum = arr.reduce((acc, val) => {
                    return acc + val;
                }, 0);
                const isSumEven = sum % 2 === 0;
                return isSumEven ? 'even' : 'odd';
            };
            console.log(assignSum(arr));

```
# Week 2

## Is Palindrome?

Challenge: A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This includes capital letters, punctuation, and word dividers.

Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.

Examples(Input ==> Output)
"anna"   ==> true

For this solution I used a Regular expression to match character combinations in the strings and several built-in methods.

```
function palindrome(str) {
   var re = /[^A-Za-z0-9]/g;
   var lowRegStr = str.toLowerCase().replace(re, '');
   var reverseStr = lowRegStr.split('').reverse().join('');
   return reverseStr === lowRegStr;
}
        
palindrome("Never odd or even");
```
## Well of Ideas

In this kata you need to check the provided array (x) for good ideas 'good' and bad ideas 'bad'. If there are one or two good ideas, return 'Publish!', if there are more than 2 return 'I smell a series!'. If there are no good ideas, as is often the case, return 'Fail!'.
```
function well(x){
  const goodCounter = x.filter((idea)=>idea==="good").length;
  return goodCounter === 0
  ? "Fail!"
  : goodCounter > 2
  ? "I smell a series!"
  : "Publish!";
} 
```

## Events

```
import React from 'react';

export class Counter extends React.Component {
  constructor(props){
    super(props);
    this.state = {
      counter: 0,
    };
    this.increment = this.increment.bind(this);
    this.decrement = this.decrement.bind(this);
  }

  increment() {
    this.setState({
      counter: this.state.counter + 1
    });
  };

  decrement() {
    this.setState({
      counter: this.state.counter - 1
    });
  };

  render() {
    return (
      <div className="counter">
        <h1 id="counter">{this.state.counter}</h1>
        <button id="increment" onClick={this.increment}>+</button>
        <button id="decrement" onClick={this.decrement}>-</button>
      </div>
    );
  }
}


```

## Thursday - React Santa Wish List

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

```
const React = require("react");

class WishlistForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { name: '', wish: '', priority: 1 };
    this.handleNameChange = this.handleNameChange.bind(this);
    this.handleWishChange = this.handleWishChange.bind(this);
    this.handlePriorityChange = this.handlePriorityChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  
  handleNameChange(e) {
    this.setState({name: e.target.value});
  }
  
  handleWishChange(e) {
    this.setState({wish: e.target.value});
  }
  
  
  handlePriorityChange(e) {
    this.setState({priority: e.target.value});
  }
  
  handleSubmit(e){
    e.preventDefault();
    this.props.send(this.state);
  }
  render() {
    return (
      <form onSubmit={this.handleSubmit}>
       Name: <input type="text" id="name" value={this.state.name} onChange={this.handleNameChange}/>
       Wish: <textarea rows="10" cols="10" id="wish" value={this.state.wish} onChange={this.handleWishChange} />
       <br />
       Wish Priority:
       <select value={this.state.priority} id="priority" onChange={this.handlePriorityChange}>
         <option value={1}>1</option>
         <option value={2}>2</option>
         <option value={3}>3</option>
         <option value={4}>4</option>
         <option value={5}>5</option>
      </select>
      </form>
    );
  }
};

```
## Week 3

# (Monday) Build Search Filter In React

React code to build a simple search filter functionality to display a filtered list based on the search query entered by the user.

```
import React, { useState } from 'react';

function Filter() {

    const list = [
        'Banana',
        'Apple',
        'Orange',
        'Mango',
        'Watermelon',
    ];

    const [filterList, setFilterList] = useState(list);

    const handleChangeSearch = (e) => {
        if (e.target.value === '') {
            setFilterList(list);
        }
    

        const filteredValues = list.filter(
            (item) =>
                item.toLowerCase().indexOf(e.target.value.toLowerCase()) !== -1
        );

        setFilterList(filteredValues);
    };
    
    return (
      
        <form>
          <label>
            Search: <input type="text" onChange={handleChangeSearch} />
          </label>
            {filterList && filterList.map((item, index) => (
                <div key={`${item}-${index}`}>{item}</div>))}
        </form>
      
    );
}

export default Filter;

```
