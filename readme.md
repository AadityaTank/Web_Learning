## Semicolons
They are optional in js

---
## function as a variable

In Js functions can be stored in variable like any other values, and can be invoked using parathesis on those variables
e.g.

    var add = function somefunc( a, b ) {
        return a+b
    }

    add(4,5)         // outputs 9
    somefunc(4,5)    // outputs 9

Js also allows us to create functions that dont have names or Anonymus functions since.

    var sub = function( a, b ) {
        return a-b
    }

    sub(5,3)    // outputs 2

Lastly if you don't want to name the function can call it or call the function as soon as you define it, you can do so by calling it inplace as follows.

    function() {
        console.log("Hello in console")
    }()
    
These are the important concepts to understand first to be able to understand the patten of clousure which is derivative of these.

---
## Closures
A closure is ability of function to remember its surrounding.
e.g.

    function parent() {
        let x = 5
        let y = function(a) {
            return x+a;
        }
        return y    // note that a function is being returned
    }

    let myFunc = parent()

    // note since y is being returned into myFunc so calling myFunc will invoke y.
    // But now y is returned OUT of parent what happens to the x since it was availabe only in parent function?

    myFunc(3)   // this returns 8 as answer. 
    
    // The value of x is remembered by the retured function y since it is in its CLOSURE (i.e its immidiate environment that it remembers)

---
Note: "remember" simply means that every time a function is returned a new copy of variables in its environment is created and maintained by js and stays attached to the function as a "Closure"

---
Now a more formal defination will be : A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

---
## Arrow Functions
Arrow functions are new way (syntax) of declaring functions in js. Example below.

    let a = () => {
        console.log("Hello there!")
    }
    a() // logs "Hello there!"

But their peculiarities are not limited to syntax. They also have slightly different behaviours than normal function in few specific contexts.
## TBC

---
## Destructuring
It is used to assign multiple variables at once, or selectively cherry pick values that are required from object (used generally in liberaries and functions). This is a reletively new notion that many of the languages are now supporting including Js.

e.g

      const [a, b] = [5, 9]      // a becomes 5 and b takes value of 9
      const {c, e, d} = {c:5, d:9} // c becomes 5, e is undefined, d becomes 9. note that variables are assigned values with perticula key
      const {y} = {x:5, y:3, z:20, l:55} // Only y value is fetched i.e. 3.

---
## Spread operator
It is used to spread out all the elements in an array or object. Say you want to pass each element of an array as parameter to function.
This operator is commonly used when you want to add or update a perticular value but are obliious to what an array or object already has.
Look at following 2 examples.

### 1.

    function sum(x, y, z) {
        return x + y + z;
    }

    const numbers = [1, 2, 3];

    console.log(sum(...numbers));   // spreading all the numbers to be x, y, z
### 2.

    let arr1 = [0, 1, 2];
    let arr2 = [3, 4, 5];

    arr1 = [...arr2, ...arr1];      // spreading numbers as input to new array
    //  arr1 is now [3, 4, 5, 0, 1, 2]
### 3. 

<sup>Find more at : [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax]</sup>

---
## Functional programming approach
There are few functions that Js supports that are taken from functional programming approach.

These are Map, Reduce, Filter, etc.
<sup>Map    : [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map]</sup>
<sup>Reduce : [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce]</sup>
<sup>Filter : [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter]</sup>