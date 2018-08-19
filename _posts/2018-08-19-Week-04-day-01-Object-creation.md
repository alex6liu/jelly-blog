---
layout: post
title:  "Week-04 day-01 Object creation"
date:   2018-08-19 18:03:20 +0800
categories: JSA
---

Reading: 

- [This, Bind method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) 
- [Gentle explanation of 'this' keyword in JavaScript](https://rainsoft.io/gentle-explanation-of-this-in-javascript) 
- [Working with Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)  

## Material Review
 - global (`window`) object
 - objects
 - functions as values
 - context
 - function invocation
 - `this`
 - `.call`
 - `.apply`
 - `.bind`
 - constructor functions
 - `class`
 - class `constructor`


### methods and this

```js
var student = {
  name: "John Doe",
  greet: function() {
    console.log(this.name);
  }
};

student.greet(); // prints greet
```

### this and bind

```js
const hawaii = {
  isSunny: true,
  temp: 55,
  unit: 'fahrenheit',
  getWeather: function() {
    console.log( this.temp + '° ' + this.unit )
    if( this.isSunny ) {
      console.log( "It's sunny over here :)" )
    }
  }
}

const london = {
  isSunny: false,
  temp: 17,
  unit: 'celsius'  
}

hawaii.getWeather() // prints 55
hawaii.getWeather.apply(london) // prints 17

const theHawaiiWeatherManInLondon = hawaii.getWeather.bind(london) // create a new function with london as a context
theHawaiiWeatherManInLondon() // prints 17

// Let's steal the hawaii weather function
london.getWeather = hawaii.getWeather 
london.getWeather() // prints 17
```

### objects, constructors and classes

#### the function constructor way

```js
function Aircraft(type){
  this.type = type;
  this.ammo = 0;
  this.maxAmmo = 8;
  this.baseDamage = 30;
  this.printMaxAmmo = function() {
    console.log(this.maxAmmo);
  };
}

var plane = new Aircraft('F16');
console.log(plane.type); // prints 'F16'
plane.printMaxAmmo(); // prints 8
```

#### the class way

This is exactly the same as above, it's just written in a different style

```js
class Aircraft {

  constructor(type) {
    this.type = type;
    this.ammo = 0;
    this.maxAmmo = 8;
    this.baseDamage = 30;
  }

  printMaxAmmo() {
    console.log(this.maxAmmo);
  }
}

// The usage of it is also the same
var plane = new Aircraft('F16');
console.log(plane.type); // prints 'F16'
plane.printMaxAmmo(); // prints 8
```
