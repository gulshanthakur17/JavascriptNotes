# Undefined and Not Defined


## Undefined

While allocating memory to all the variables and functions, Javascript allocates a special keyword, `undefined` to all variables to imply that the variable has been defined further in the program but it's value has not yet been initialized.

## Not Defined

When we try to access a variable has not been declared at any point in the whole code then we get this exception which implies that the variable has `not been defined` anywhere in the code.

```

var a;

console.log(a)

if(a === undefined) {
    console.log("a is undefined")
}
else {
    console.log("a is not undefined")
}

```

Here, we will get `a is undefined` as our output as we haven't initialized it yet.

## Javascript is a loosely typed language

In javascript we can use the same variable to store different types of values as per our requirements. In other words, if we want to store a number to a variable and after a certain operation we want to store a string to the same variable we can do it easily without running into any error in javascript.

```

var a;
console.log(a) // undefined

a = 10
console.log(a) // 10

a = 'hello world' 
console.log(a) // hello world

```

The above code works perfectly fine in javascript as it is a `loosely typed language / weakly typed language`. This makes javascript more flexible.

### Never do this mistake

```

a = undefined

```

`Undefined is a placeholder` which is kept inside a variable to imply nothing was stored till now in that variable. Although storing undefined to a variable won't give any error but it is not a healthy practice as it has it's own purpose and it may be misleading for other developers who are reading your code. 