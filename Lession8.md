# Let & Const Declarations

## Are let and const declarations hoisted?

Yes they are but they're in the temporal deadzone for the time being.

```
console.log(b)
let a = 10
var b = 100
```

We have learnt that hoisting allows us to access a variable even before it is declared. It uses the `undefined` value as it's default value before the variable is declared.

If we try the same with a which is declared using let, we will get an error saying: `Cannot access 'a' before initialization`.

In case of var, as we start the execution the var variable is allocated memory in the `Global` and in case of let and const they are allocated memory in a different memory space. And we cannot access these values unless we put some value in these variables.

## Temporal Dead Zone

A `temporal dead zone` (TDZ) is the area of a block where a variable is inaccessible until the moment the computer completely initializes it with a value.

## Facts

- We cannot redeclare a `let`/`const` variable.
- `const` is meant to be declared and intialized in the same line.
- If we try to reassign a const variable then it will give us a `TypeError`.
- If we don't initialize the const variable as soon as we declare it, it will give us a `SyntaxError`.
- When we don't find a specific variable in the whole scope then it gives a `ReferenceError`.

## Suggestions

- When we don't have to change the variable value use `const` or at least `let` to avoid unexpected errors.
- Don't use `var` much
- `Temporal Dead Zone` can lead to unexpected errors as well and the best way to avoid this is to put declaration and initializations on the top. Basically here we are shrinking the temporal dead zone.