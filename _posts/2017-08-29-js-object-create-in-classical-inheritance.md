---
layout: post
title: JavaScript - Object.create in Classical Inheritance
---

You've probably seen the `Object.create` pattern was used to mimic `Class`ical inheritance in JavaScript ES5 such as:

```javascript
function Animal() {
}

Animal.prototype.say = function() {
  console.log('Say!');
};

function Dog() {
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;
```

You may be curious about why `Object.create` is used here to make inheritance. So let's figure out why it is needed for proper inheritance.

the following example can also be used to mimic inheritance:

```javascript
function Animal() {
}

Animal.prototype.say = function() {
  console.log('Say!');
};

function Dog() {
}

Dog.prototype = new Animal();
Dog.prototype.constructor = Dog;
```

I think you've already noticed this code can cause a side-effect. Copying prototype with `new Animal()` can cause side-effect, because it will call `Animal` constructor once. and it's unnecessary action.

So we need to copy `Animal.prototype` without calling the constructor. and using `Object.create` is the answer.

## References

- [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/create](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/create)
