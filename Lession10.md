# Closures

```
function x() {
    var a = 7
    function y() {
        console.log(a)
    }
    y()
}
x()
```

Here we'll get 7 as the output and this code is actually closure.

## What is closure actually?

`Closure` basically means that a function is bind together with it's lexical scope.

In the above code, the function y was bind to the variables of x so it formed a closure and it had access to it's parent's resources.

According to [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures), Closure is the combination of a function bundled together with references to it's surrounding states (the lexical environment).

`PS: Javascript allows to pass functions as parameters and return function from a function.`

## Few Examples

### Example 1:

```
function x() {
    var a = 7
    function y() {
        console.log(a)
    }
    return y
}

var z = x()
console.log(z)
```

Here we will get the whole function y as the output since x return the function y and stores it into z.

After returning y, x has been removed and y is stored in z. Now when z is executed and it looks for the variable a and it is found as due to closure even after x is discarded, y function remembers it's lexical environment. 

So basically when we returned y, we not only returned the function but also it's lexical envvironment which helped us find the value of a. Hence we can say closure plays an important role here.

### Example 2:

```
function x() {
    var a = 7
    function y() {
        console.log(a)
    }
    a = 100
    return y
}

var z = x()
console.log(z)
```

Here a has been updated and since y remembers the reference to the memory location of a, it will take the updated value of a even if we change it outside the function y.

### Example 3: 

```
function z(){
    var b = 900
    function x() {
        var a = 7
        function y() {
            console.log(a, b)
        }
        a = 100
        return y
    }
    x()
}
z()
```


If we put whole code inside another function. Will it still be a closure? YES!

y will still have a closure with x and it will also have a closure with z which is it's parent's parent.

## Uses of Closures:

- Module Design Pattern
- Currying
- Functions like once
- memoize
- maintaining state in async world
- setTimeouts
- Iterators
- and many more...