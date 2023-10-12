# How Function works?

```
var x = 1;
a();
b();

function a() {
    var x = 10;
    console.log(x);
}

function b() {
    var x = 100;
    console.log(x);
}
```

## If we have same variable names then how does Javascript work?

When we run the above program, the global execution context will be created. Firstly, we'll be allocating memory to x and the other 2 functions.

At first before execution x will store undefined and a() and b() will be pointing to the full function code. Then the execution starts and 1 is stored to x.

Now moving on to a(), a new execution context will be created for this function and we will allocate memory and then execute the code in this funciton. In this context, we will store and allocate memory to the new x variable that belongs to the scope of this function. We won't be able to access it's value outside of this function. Also this execution context will be pushed inside the call stack.

After the execution, the whole execution context of a() will be deleted and the call stack will pop out it's execution context and the control goes back to global execution context. 

Now we move to b(), a new execution context is created again and everything that happened in a() will be repeated but this time the value of x will change as we have defined a different value of x in this function. 

We will move back to the global execution context and now we have a console log in this line. This line will look for x in the local space which is the gec itself and we will get the global value of x in the console.

Now there's nothing more to execute and the whole code has been executed then the gec will be popped out of the call stack and the whole memory that was allocated for the execution of the program will be taken back.