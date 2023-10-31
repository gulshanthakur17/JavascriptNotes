# Most asked Interview Questions - Closure

```
function x(){
    var i = 1
    setTimeOut(function () {
        console.log(i)
    }, 3000)
    console.log("Namaste Javascript")
}
x()
```

Javascript will print Namaste Javascript before waiting for setTimeOut. Because JS waits for none. 

```
function x(){
    for(var i = 1;i <= 5; i++){
        setTimeOut(function () {
            console.log(i)
        }, i * 1000)
    }
    console.log("Namaste Javascript")
}
x()
```


We might expect the above code to print 1 2 3 4 5 after 1 sec, 2 sec, 3  sec ....
But it will print 6, 5 times in 1 sec 2 sec 3 sec... because of Closure. The variable i for each loop is refering to the same memory location where the value has been updated to i.

To fix this we can use let instead of var in the loop.

```
function x(){
    for(let i = 1;i <= 5; i++){
        setTimeOut(function () {
            console.log(i)
        }, i * 1000)
    }
    console.log("Namaste Javascript")
}
x()
```

Here, the copy of i in each iteration is a new copy of variable and setTimeOut will take the function where the bound of i is new. 

Since let is block scope it creates a new copy and it does'nt creates this with var.

Incase we are not allowed to use let then closures will help us to fix this. 

```
function x(){
    for(var i = 1; i <= 5; i++){
        function close(i){
            setTimeOut(function () {
                console.log(i)
            }, i * 1000)
        }
        close(i)
    }
    
    console.log("Namaste Javascript")
}
x()
```