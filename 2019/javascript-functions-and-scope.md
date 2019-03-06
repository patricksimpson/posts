---
title: "Scope in JavaScript Functions"
date: "2019-03-06  1:27 PM"
summary: ""
tags: ["javascript", "programming", "blog"]
---

I was trying to explain scoping in JavaScript the other day and I thought it would be good to post a little
about JavaScript scoping.

**What is scope?** [Scope](https://en.wikipedia.org/wiki/Scope_(computer_science)) is just the _parts_ of your code that are currently available or in otherwords... the variables that are currently visible.

## Lexical Scope in JavaScript

JavaScript uses something called “lexical” scoping, or scopes which are nested within each other.
This type of scope means that all functions and variables declared are “available” inside inner functions.
Variables declared within functions are not "accessible" outside of that function:

    // outer area, global (in the browser it’s `window`).

    function main() {
      // Main has access to `window`, which is a global variable.

      const a = true;

      function inner() {
      // has access to the `main` function scope (lexical)
      console.log(a); // true
      const hello = 'world';
      }
      inner();
    }

    main();
    console.log(hello); // undefined, out of scope.

## So, What is `this`?

In javascript, you may have encountered `this`.

`this` is a [keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) in JavaScript.

`this` is a reference the current [executable scope](http://www.digital-web.com/articles/scope_in_javascript/).

For classes, methods, and aysnc JavaScript…  it’s very important to know, that you can also `bind` whatever you’d like to `this`, but often it's
good to bind the current executable scope. (see arrow functions below).

## Bind

Bind is a way you can “define” the `this` of a function.

This works like `main.bind(someVariable);` Note, bind doesn’t call the method.
When called the `someVariable` will be the `this` variable inside the function.
You can do this all at once with `call`. `main.call(someVariable);` will invoke the main function and assign `someVariable` to `this`.

Example:

    Const someVariable = ‘hello’;

    function main() {
      console.log(this); // hello
    }

    main.call(someVariable);

## Arrow Functions

[Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), such as `=>`, is syntactic sugar around a function expression or an anonymous function...

What’s happening with an arrow function? Why is it used (other than, hey it's easy to type)?

Typically you may see a call: `const main = () => { console.log(this); }`

Arrow functions (function expressions) always bind the outer function scope `this` at execution.
Essentially, `(function main() { console.log(this)).bind(this);`

This used to be done as follows:

    var that = this;
    setTimeout((function() { console.log(that); }), 1);

In CoffeeScript, it was `=>` (we called it a fat arrow), "hacked" the ` var that = this;` pattern to your function, allowing you to have gain context of the callee's scope.

Thankfully, arrow functions was adopted in ES6 and we can thank CoffeeScript for it. (Thanks, [Jeremy Ashkenas](https://en.wikipedia.org/wiki/Jeremy_Ashkenas)!)

## Much more...

There's a lot here and there is much more to cover.
Feel free to ask me questions... even writting this article, cleared up a few things for me.
