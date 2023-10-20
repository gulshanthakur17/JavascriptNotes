# Block Scope & Shadowing

## What is a block

A block is defined by two curly braces like:

```
{
    // Compound Statement
    var a = 10
    console.log(a)
}
```

A block is also known as `Compound Statement`. It is used to combine multiple js statement into group. We group the statement together so that we can use it where js expects one statement.

For example, after an if statement js expects something but we know that if statement only runs the first line below it. So to run multiple line we put them inside a block and place this block below the if statement so that js will think we are running a single line of code but it actually has multiple lines.

```
if(true) {
    console.log('Yes')
    console.log("It's True")
}
```

## What is a block scope ?

Block Scope means what all variables and functions we can access inside this block.

To check we will use the three declaration types and check how they behave in a block.

```
{
    var a = 10
    let b = 20
    const c = 30
}
```

After observation we see that, within the block scope we have `b` and `c` where as `a` is hoisted in the Global scope.
Once js has finished executing the block, we will see that b and c are removed from the scope and we only have a because it's scope is global.

## What is Shadowing ?

If we have a same name variable outside a block then the block variable shadows the other variable which was outside the block, if the block is declared after the outside variable and in the future if we try to access the variable outside the block we will still get the shadowed value as var has global scope.

In case of let, shadowing will change the value only within the block and outside the block it's value will remain same as previous.

## Waht if we try to shadow a let variable inside a block as var ?

The Js compiler won't allow us to do that and will throw an Error: `SyntaxError: Identified 'a' has already been declared` but we can do it vice-cersa.

Reason: If a variable is shadowing something then it should not cross the scope of the original variable. if we shadow a let using var then the scope will be crossed as var is global scope and let is Script scope. These scopes are lexically present and so if we try to print a variable, it's nearest declaration will be printed.

```
const a = 20
{
    const a = 200
    {
        const a = 100
        console.log(a)
    }
}
```

The above code will print `100`