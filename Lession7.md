# The Scope Chain

```

function a() {
    console.log(b)
}

var b = 10
a()

```

When we run the above code, js engine will try to find b in the function a's local memory and then it will check for the same in the global memory and finds the value of b and print it.

```

function a() {
    function c() {
        console.log(b)
    }
}

var b = 10
a()

```

This code can also access b
But, if we have the code

```
function a() {
    var b = 10
}

a()
console.log(b)
```

This will give an error, `ReferenceError : b is not defined`

## What is scope ?

`Scope` means where we can access a specific variable or function in a code.

## Lexical Environment

Whenever an execution context is created, a lexical environment is also created. `Lexical` means in `hierarchy`. Function c is inside a, so that means function c is lexically in a.
Whenever the execution context is created we also get the lexical environment of it's parent. So c will get access to lexical environment of a and a will get lexical environment of global execution context. And Global execution context also contains the parent lexical environment which points to null as it is not having any parents.

## The Scope Chain

The whole chain of lexical environment is known as `the scope chain` and it defines whether a variable or function is present in the scope chain or not. If the whole scope chain is exhausted and we don't find the variable or function that means it's not present in the scope.