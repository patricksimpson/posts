---
title: "Scope in JavaScript Functions"
date: "2019-03-06  1:27 PM"
summary: "Let's talk about this and that... I mean, scope in JavaScript functions!"
tags: ["javascript", "programming", "blog"]
---

I was explaining scoping in JavaScript the other day and I thought it would be good to post a little
about it.

**What is scope?** [Scope](https://en.wikipedia.org/wiki/Scope_(computer_science)) is just the _parts_ of your code that are currently
available. In otherwords, the _variables_ (parts) that are currently available or visible. In JavaScript, it's called _lexical scope_. 

## Lexical Scope in JavaScript

JavaScript uses “lexical” scoping: scopes which are nested within each other.

This model means that all functions and variables declared are _available_ inside inner functions.
Variables declared within functions are not _accessible_ outside of that function. 

Example: 

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
   
   
Breaking that example down: 

  - `main` lives in the global scope.
    - has access to global scope variables.
    - does not have access to the `inner` declared variables, like `hello`.
  - `inner` lives in the `main` scope as well as the global scope.
    - has access to both the global, and the main variables.

## And What is `this`?

In JavaScript, you may have encountered `this`.

 - `this` is a [keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) in JavaScript.
 - `this` is a reference the current [executable scope](http://www.digital-web.com/articles/scope_in_javascript/).

For classes, methods, and aysnc JavaScript, you can `bind` whatever you’d like to `this`, but often it's
good to bind the current executable scope. (Say what?) 

Example: 

    this.classMethod = this.classMethod.bind(this);

This example is often seen inside class constructors. This approach allows for these methods (or functions) to have the access to the variables defined in that class instance. `this` in _this_ case applies to the instance of the class.

You can have multiple instances of the same class, each would have their own, very different `this` context. (It would be bad otherwise.🤯)

## Bind

Bind is a way you can “define” the `this` of a function.

This works like `main.bind(someVariable);` Note, bind doesn’t call the method.
When called the `someVariable` will be the `this` variable inside the function.
You can do this all at once with `call`. `main.call(someVariable);` will invoke the main function and assign `someVariable` to `this`.

Example:

    const someVariable = 'hello';

    function main() {
      console.log(this); // hello
    }

    main.call(someVariable);
    
Again, `bind` is just a way to set the value of `this` in a function.

## Arrow Functions

[Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), such as `=>`, is syntactic sugar around a function expression or an anonymous function...

What’s happening with an arrow function? Why is it used (other than, hey it's easy to type)?

Typically you may see a call: `const main = () => { console.log(this); }`

Arrow functions (function expressions) always bind the outer function scope.

So instead of using `this.classMethod = this.classMethod.bind(this)`, you can use `const classMethod = () => { }` which
will give you the class `this` binding you expect. Pretty cool. You can really start cleaning up those class contructors now ☺️!

## `this` and `that`

The _old_ way around scoping issues, was to provide a variable that would caputre the current scope context.

Say hello to an old friend: `var that = this;`, yuck. 

Example: 

    var that = this;
    setTimeout((function() { console.log(that); }), 1);

CoffeeScript it was `=>` called a fat arrow... It was a shortcut way to do this: `var that = this;` pattern. This allowed you to have gain context of the callee's scope, without all those extra `that = this` stuff. 

Thankfully, arrow functions was adopted in ES6 and we can thank CoffeeScript for it. (Thanks, [Jeremy Ashkenas](https://en.wikipedia.org/wiki/Jeremy_Ashkenas)!)

## Much more...

There's a lot here and there is much more to cover.
Feel free to ask me questions... even writting this article, cleared up a few things for me.
