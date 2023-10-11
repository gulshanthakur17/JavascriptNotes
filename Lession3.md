# Hoisting

JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables, classes, or imports to the top of their scope, prior to execution of the code. In reality, it doesn't moves the code instead it creates a global execution context in the beginning which helps us to access the variables and function.

## Let's see what actually happens there

Consider this code:

```

getName() // line 1
console.log(x) // line 2

var x = 7 // line 3

function getName(){ // line 4
    console.log("Namaste JavaScript") // line 5
} // line 6

```

If we run this code, we will get the function's log and undefined on our console.

and if we remove line 3, then it will give us an error, `x` is not defined. 

So what's the difference between `undefined` and `not defined`. 

Undefined tells us that the variable is not defined yet but it has been defined in the program in the following lines. 
While Not Defined tells us that the variable is not defined in the whole program.

In case we try to `console.log(getName)` then we'll get the function in our console.

> We can refer to the previous lecture's notes to understand why the above phenomenon occurred

```
var getName = () = {
    console.log("Arrow Function")
}
```

In the above code we will not get the whole function in `getName` variable as it is not a function 
but a variable that stores the value returned by the arrow function.