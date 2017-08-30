---
layout: post
title: JavaScript - var, let, const
date: 2017-08-27 00:00:00 +0900
---

As you know, There was only `var` keyword for variable declaration before ES2015. but Modern JavaScript have introduced `let` and `const` keywords for it.  
So let's figure out the differences between `var` and the others.

## Function Scoped

JavaScript's `var` has slightly different scope than any other programming languages. and it's called **Function Scope**.  

the following examples are all properly working JavaScript codes.

```javascript
function a() {
  if (true) {
    var x = 10;
  }
  console.log(x); // prints 10
}
```

```javascript
function b() {
  for (var i = 0; i < 10; i++) {
    var k = '99';
  }
  console.log(k); // prints '99' 
}
```

You may feel it's something strange. but above codes are all properly working codes becauseof **Function Scope**.

With **Function Scope**, All variable declarations inside function are all alive along with the function that variables was declared.

## Hoisting

Here is one more strange rule which `var` has called **Hoisting**. (Personally, I couldn't understand why Hoisting was needed for JavaScript)

These examples are all properly working JavaScripts.

```javascript
function a() {
  x = 10;
  console.log(x); // prints 10

  var x;
}
```

```javascript
function b() {
  y = 100;

  if (false) {
    var y;    // even this code will not be evaluated, you can delcare a variable like this
  }

  console.log(y); // prints 100
}
```

Basically, JavaScript Parser parses the function and finds out all `var` variable declarations and moves it to the top of the function.
and this feature is called **Hoisting**.

So the above function `b` can be converted like this:

```javascript
function b() {
  var y;
  y = 100;

  if (false) {
  }

  console.log(y);
}
```

## and `let`

All those weird language features makes ES2015(ES6) to do introduce the `let` keyword.

`let` has following differences compare to `var`:

- **Block Scoped**
- **Hoisting** but with **Temporal Dead Zone**

Then, Let's figure out more about these differences.

### Block Scoped

With `let`, the following examples are no more working like the examples with `var`.

```javascript
function aa() {
  if (true) {
    let x = 10;
  }
  console.log(x); // a is not defined
}
```

```javascript
function bb() {
  for (let i = 0; i < 10; i++) {
    let k = '99';
  }
  console.log(k); // k is not defined
}
```

because `let` is **Block Scoped**, variables using `let` will only be alive for the block (`{` `}`) that variable was declared.

and I think this is more understandable rule than **Function Scoped**.

### Temporal Dead Zone

`let` is still hoisted like `var` but the additional rule called **Temporal Dead Zone** has been added. So the following example is no more working with `let` variables.

```javascript
function a() {
  x = 10;         // a is not defined
  console.log(x);

  let x;
}
```

In **Temporal Dead Zone** semantics, you can't access the variable which hasn't been initialized. so a `let` variable declaration still be hoisted, but it works like its not hoisted.

I think simple hoisting only makes codes hard to maintain.
with `let` variables, Now you can make more easier to maintain JavaScript codes.

## Then... What is `const`?

In Programming, all **mutable** variables can be considered as **evil**. because it changes program state and many mutable variables makes it impossible to track the state you are changing.

So Basically, we need to make variables immutable as possible. `const` keyword is needed for it.

It's like a `let` keyword, but when you assign the variable once, you can't **re-assign** the variable.
> The actual value of the variable is not immutable, you can still change the properties of the value

```javascript
function a() {
  const x = 10;

  x = 100; // Error!
}
```

like the above example, you can't re-assign the `const` variable. and `const` must be declared with initial assignment.

```javascript
function b() {
  const y; // Error!
  y = 100;
}
```

You can use `const` keyword for variables that only needs one assignment. you can treat the `const` variables as immutable.

`const` keyword allows you to create more maintainable code. So I personally recommend to use it as many as possible. 

## Conclusion

- `var`: Function Scoped, Hoisting
- `let`: Block Scoped, Hoisting + Temporal Dead Zone
- `const`: `let` + Immutable

## References

- [https://developer.mozilla.org/ko/docs/Glossary/Hoisting](https://developer.mozilla.org/ko/docs/Glossary/Hoisting)
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
- [http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)
