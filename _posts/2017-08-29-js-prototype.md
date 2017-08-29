---
layout: post
title: JavaScript - Understanding Prototype
date: 2017-08-29 21:00:00 +0900
---

There is a very hard to understand concept which JavaScript has called **Prototype**. You've already seen a lot if you have an experience with JavaScript.

Many books and articles describing prototype are out there, but i just write this yet another article about prototype to improve my understanding.

Actually many people calls both **Prototype Object** and **Prototype Link** a **Prototype**. So it becomes beginners to understand difficult.

So let's figure out the differences between Prototype Object and Prototype Link.

## Prototype Object vs Prototype Link

When you declare a Function, then the Function object have its own **Prototype Object**.

the **Prototype Object** is just another plain object, and it has the parent Function on its `constructor` property. (Circular Reference)

```javascript
function Animal() {
}

console.log(Animal.prototype.constructor === Animal); // prints true
```

And when you instantiate new object with the Function, the instantiated object will be linked with the **Prototype Object** just like this:

```javascript
function Animal() {
}

Animal.prototype.say = function() {
  console.log('this is animal');
};

var animal = new Animal();
console.log(animal.__proto__ === Animal.prototype); // prints true
```

You may notice that instantiated `animal` object has strange `__proto__` property. and Yes, `__proto__` is a **Prototype Link**.

## How Prototype works

**Prototype Object** is just a special plain object which all Function objects have.

and **Prototype Link** is a just a link to original **Prototype Object**.

With **Prototype Link**, You can call a function which is located at the **Prototype Object** on the instantiated object, for example:

```javascript
function Animal() {
  this.name = 'animal';
}

Animal.prototype.say = function() {
  console.log('This is ' + this.name);
};

function Dog() {
  this.name = 'dog';
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

var dog = new Dog();
dog.say(); // call Animal.prototype.say with 'dog' context, prints 'This is dog'
```

In the example, when you call a `say` function on `dog` object. JavaScript engine will find `say` function on the `dog` object first, and if can't find it then it will find the function on the its `__proto__` object, and so on. and finally the found function is called with `dog` object context. (its like: `Dog.__proto__.say.call(dog);`)

And finding the calling function can be following multiple prototype links, it's called **Prototype Chain**.

the following figure is describing the prototype relations for the example:

![]({{ site.baseurl }}/assets/js-prototype-figure.png){: .center}

## Summary

- **Prototype Object**: a Special plain object on all Function objects
- **Prototype Link**: a Link to the Prototype Object on all objects.
