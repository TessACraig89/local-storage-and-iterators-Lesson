# Local Storage and Iterators

### Objectives
*After this lesson, students will be able to:*

- Describe what an API is
- Use local storage to persist data in the browser
- Use Map, Filter, and Reduce to iterate over data and perform actions on each piece of data


### Preparation
*Before this lesson, students should already be able to:*
- Get and set data in JavaScript Objects
- Use for loops to iterate over arrays
- Use callback functions


## What is LocalStorage

LocalStorage is: 

- An object where you can store data in key value pairs
- LocalStorage itself is a property of the Window object
- It is a way to persist data even when the page refreshes. 
- Each **domain** your browser visits can create its own localStorage object. 
- LocalStorage is part of the Window object's API. 

### APIs, what are they? A brief introduction.

API stands for Application Program Interface. When people say API most of the time they mean a *web api*, like the Twitter API, the Google Maps API, etc.

However, anything in computer science that has an interface has an API. The API defines the interface. 

Usually when we think of interfaces, we thing of things like Gooeys (graphic user interface), but interface is just how you interact with something. For example, the way you interface with a rotary phone is by spinning the dial. 

A JavaScript Object has an interface! A string has an interface. And the browser's Window has an interface. Part of that interface is an object called LocalStorage, where we can store stuff. 

### Let's Practice :computer: 

 ```
- Find a partner!
- Open your chrome console and type window to check out the window object 
- Enter window.localStorage and check that out. What do you see? What's it look like the site is using localStorage for?
- Check out a couple more of your favorite websites and look at what they are doing with localStorage, and discuss this with your partner.
- Thumbs up when done
- 6 min.
```

## Using LocalStorage

LocalStorage has an API too! It has to so we can do stuff with it. LocalStorage's API is *super simple*. There are only three methods:

```
localStorage.setItem('myCat', 'Grimm');

var cat = localStorage.getItem("myCat");

localStorage.removeItem("myCat");
```

This works very much the same way as getting and setting attributes in a JavaScript Object, just with a different syntax.


:eyes: Window is top level global scope in the browswer, so window.anything is also available as anything

```javascript
window.localStorage === localStorage;
// true
window.foo === foo
// true 
```


### LocalStorage in JS Racer Demo

:eyes:


## Iterators: Map, Reduce, and Filter

### Map 

We use map when we want to take an array, do something to each item, and get back a new array with the new values. We **map** the values into a new array

For example, mapping an array of fahrenheit temperatures to celsius:

```javascript
const fahrenheit = [0, 32, 45, 50, 75, 80, 99, 120];

const celsius = fahrenheit.map(elem => Math.round((elem - 32) * 5 / 9));

celsius //  [-18, 0, 7, 10, 24, 27, 37, 49]
```

*example from https://danmartensen.svbtle.com/javascripts-map-reduce-and-filter*

### Let's Practice :computer: 

 ```
- In a JS file, create an array of numbers between 0 and 1 called decimals.
- Example: [.3, .09, .44, .8]
- Use .map to create a new array of percentages that looks like this: ['30%', '09%', '44%', '%80']
- Copy-paste your code as a reply to this instruction in Slack
- 8 min.
```

### Reduce

Reduce is used when you want to accumulate data of some kind from an array. It works great for summing the numbers in an array! How it works is you call it on your array, and pass it a call back with at least two parameters. The first parameter tracks the total, the second represents each item in the array. 

Here's how to do it using a for loop:

```javascript
const numbers = [10, 20, 30, 40] // sums to 100
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
  sum += numbers[i]
}
console.log(sum);
// 100
```

And how to solve it with **reduce**: 

```javascript
const numbers = [10, 20, 30, 40] // sums to 100
let sum = numbers.reduce((total, amount) => total + amount)
console.log(sum);
// 100
```

### Let's Practice :computer: 

 ```
- In a JS file, create an array of numbers called prices.
- Example: [.3, 7.09, 10.44, 6.8]
- Write a function that sums the prices using reduce, and then adds an 8 percent sales tax. 
- Copy-paste your code as a reply to this instruction in Slack
- 8 min.
```

### Filter

Filter takes an array, and filters it! It returns a new array based on some criteria being met. The criteria is checked by running a callback function and seeing if it evaluates to true on each item. Let's look at the code! 

:eyes:

```
const numbersArray = [2, 4, 5, 9, 8];
const numbersBelowSix = numbersArray.filter((number) => number < 6 );
// [2, 4, 5]

const tasks = [{id: 1, name: "darn socks", duration: 180}, {id: 2, name: "eat lunch", duration: 40}]
const difficultTasks = tasks.filter((task) => task.duration >= 120 );
// [{id: 1, name: "darn socks", duration: 180}]
```

### Conclusion
- An API is the interface that a program has for other code, humans, or pretty much anything to interact with it. 
- Put another way, an API is the interface a program *exposes*. Its what a program is available to be used for. 
- .map, .reduce, and .filter are all part of a JavaScript array's interface. 
- .map, .reduce, and .filter iterate over arrays and perform tasks on them
- anything you can do with these methods can be done with for loops, but sometimes these methods are more readable, and they are almost always more concise. 


### Further readings
https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage
https://danmartensen.svbtle.com/javascripts-map-reduce-and-filter
https://code.tutsplus.com/tutorials/how-to-use-map-filter-reduce-in-javascript--cms-26209
http://adripofjavascript.com/blog/drips/boiling-down-arrays-with-array-reduce.html
