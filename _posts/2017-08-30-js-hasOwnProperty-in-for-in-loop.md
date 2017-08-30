---
layout: post
title: JavaScript - hasOwnProperty in for-in loops
date: 2017-08-30 21:00:00 +0900
---

In most programming languages, iterating over an object (dictionary or map) is natively supported. and JavaScript supports it as well.

You've might seen iterating keys over object in JavaScript looks like this:

```javascript
var obj = {
  a: 1,
  b: 2
};

for (var k in obj) {
  if (obj.hasOwnProperty(k)) {
    console.log(k); // prints a, b
  }
}
```

Actually the following code might be working as well:

```javascript
var obj = {
  a: 1,
  b: 2
};

for (var k in obj) {
  // no hasOwnProperty check
  console.log(k); // prints a, b
}
```

Then, You might say "Why we need additional useless `hasOwnProperty` check?", and feel that this is useless and not natural. (Frankly, I thought so)

But this is not useless, this is very important to make your code safe and to make it always do right thing.
because JavaScript is too open to modify its inner implementations. Such as **You can easily modify Object.prototype** which is base prototype of all objects.

the following code is a simple example for messing up `for...in` loop which has no `hasOwnProperty` check by modifying Object.prototype:

```javascript
var obj = {
  a: 1,
  b: 2
};

Object.prototype.haha = 3;

for (var k in obj) {
  console.log(k); // prints a, b, haha
}
```

Someone (some libraries or some dependencies) could touch Object.prototype on your program context in anytime, Without `hasOwnProperty` check, your `for...in` loop might be iterating unexpected keys. **So you need to make your `for...in` loop safe using `hasOwnProperty` check.**

## Object.keys()

In ES5+, You can use `Object.keys()` to get its own enumerable keys of an object as well. and it will be much safer and easier to understand.

the following code is one with `Object.keys()`:

```javascript
var obj = {
  a: 1,
  b: 2
};

Object.prototype.haha = 3;

var objKeys = Object.keys(obj);
for (var k in objKeys) {
  console.log(k); // prints a, b
}
```

It's simple and safe.

## References

- [JavaScript Patterns by Stoyan Stefanov](http://shop.oreilly.com/product/9780596806767.do)
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)
