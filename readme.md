### Semicolons
They are optional in js

### function as a variable

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

### Closures
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

Note: "remember" simply means that every time a function is returned a new copy of variables in its environment is created and maintained by js and stays attached to the function as a "Closure"


Now a more formal defination will be : A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.
