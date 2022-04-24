## Function Currying in JavaScript

Javascript is a multi-paradigm language that allows you to freely mix and match object-oriented, procedural, and functional paradigms. Recently there has been a growing trend towards functional programming. The functional programming style not only attempts to pass functions as arguments, a.k.a callbacks, but also returns back functions as well. This feature of functional programming gives us many new and useful concepts. One of these concepts is Currying.

In this article, we will take a look at what currying is and how it helps us make our code clean and much simpler.

## What is Currying?

Before diving into currying, we first need to understand the *arity* of a function. The *arity* of a function is basically the number of arguments it requires. 

Consider these two examples -

```
function addTwo(a, b) {
  return a+b;
}

function addThree(a, b, c) {
  return a + b + c; 
}

``` 

In this case, the arity of the function `addTwo` is 2 and the arity of the function `addThree` is 3. 

Currying a function means to convert a function of N arity into N different functions of arity 1.

** In much simpler words, currying is the process of restructuring the function so that it takes only one argument and then returns another function that takes the next argument, and so on. **

To give you a sense of how this could work, let's create a couple of functions -

```
// Un-curried function
function add(x, y) {
  return x + y;
}

// Curried function
function addCurried(x) {
  return function(y) {
    return x + y;
  }
}

add(1, 2);  // Returns 3
addCurried(1)(2);  // Returns 3

``` 
Notice the difference between the two. The first function is a simple function that takes two parameters -  `a` and `b`, and adds them. On the other hand, the second function `addCurried` takes only one argument i.e `a`, and returns another function which takes `b` as the argument. Both give us the same result.

Currying can be helpful when we can't provide all arguments to a function at one time.

Each function call can be saved into a variable, which will hold the returned function reference that takes the next argument when it's available. Let's take another example to understand this better -


```
// Curried function
function greet(msg) {
  return function (name) {
    console.log(msg, name);
  };
}

let english = greet("Hello,");
let spanish = greet("Hola,");
let german = greet("Geuten Tag,");

german("Dwight"); // Prints "Geuten Tag, Dwight"

spanish("Oscar"); // Prints "Hola, Oscar"

english("Michael"); // Prints "Hello, Michael"
english("Jim"); // Prints "Hello, Jim"

``` 
Notice how currying helps us avoid passing the same variable again and again. In this case, the variable `msg`, which will print  "Hello" when called using `english`. This is a great strategy to avoid frequently calling a function with the same argument.

### ES6 Pattern
Currying is part of functional programming and such curried functions can also be easily written using the arrow function syntax in ES6 for more cleaner and elegant code in the following way :

```
const addCurried = x => y => x + y;

addCurried(1)(2);   // Returns 3
``` 
### Partial Application Function
When we talk about currying, the concept of Partial Application Function is bound to come up. Currying and Partial application function are almost identical concepts with one significant difference.

Partial application function is a function that returns another function but each returned function can take multiple arguments. In currying, the returning function can only take one argument.

Let's take a simple example to demonstrate this difference- 

```
// Curried function
function addCurried(x) {
  return function (y) {
    return function (z) {
      return x + y + z;
    };
  };
}

// Partial Application function
function addPartial(x) {
  return function (y, z) {
    return x + y + z;
  };
}

addCurried(1)(2)(3); // Returns 6
addPartial(1)(2, 3); // Returns 6

``` 
The implementation of both these concepts totally depends upon the use-case and the availability of the arguments at that point in time. But they definitely help us write more cleaner and elegant code.

### Wrapping Up 

Currying is an incredibly useful concept when it comes to functional programming with Javascript. As seen, using currying we can have functions that are more definite in what they do, avoiding potential repetition in our code, which ultimately leads to simplification of our code.

** If you liked what you read, connect with me on Twitter - [@afraz_momin](https://twitter.com/afraz_momin).
I plan to write similar articles on JavaScript in the coming days! **








































