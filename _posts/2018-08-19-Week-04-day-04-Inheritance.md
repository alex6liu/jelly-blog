---
layout: post
title:  "Week-04 day-04 Inheritance"
date:   2018-08-19 18:33:20 +0800
categories: JSA
---

## Material Review
 - Object.create()
 - prototype
   - .isPrototypeOf()
   - .setPrototypeOf()
 - prototype chain
 - class
 - inheritance
   - extends
   - super()
   
   
**parent.prototype = child.__proto__**

### Prototype
```javascript
function Car(km) {
   this.km = km;
}

Car.prototype.ride = function(km) {
   this.km += km;
}

const volvo = new Car(80000);
volvo.ride(120);
console.log(volvo.km); // 80120

// Let's mess with the km via introducing a new function on the Car prototype
// it will be available for the objects created from it
Car.prototype.hackKilometerClock = function() {
    this.km = 3;
}

volvo.hackKilometerClock();

//yay we can crank up the price :)
console.log(volvo.km); // 3
```

### Inheritance with ES6

```javascript
// create the inherited class

class Foods {
  constructor(sound) {
    this.sound = sound;
  }

  serve() {
    console.log(this.sound)
  }
}

// Pizza inherits Foods

class Pizza extends Foods {
  constructor(sound, price) {
    super(sound);
    this.price = price;
  }

  cost() {
    console.log(this.price);
  }
}

// let's fire it up and see how is it works

const firstPizza = new Pizza('Chew', 1000);

firstPizza.serve();
firstPizza.cost();
```