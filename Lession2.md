# What happens when we run a JavaScript program?

An execution context is created.

# How this works?

Let's take a code:

```
var n = 2
function square(num){
var ans = num \* num
return ans
}
var square2 = square(n)
var square4 = square(4)
```

## First Phase:
Firstly Js skims through the program and stores undefined to all variables and the function to all functions

## Second Phase:
Once again Js goes through the whole program line by line and executes the program

| Memory(Phase 1 / Phase 2) | Code |
| :---: | :---: |
|n : undefined / 2 | Memory Code (New execution context is created when we call a function)|
| square : {...} | |
| num : undefined / 2 / 4 | return keyword states that return the control to the parent |
| square2 : undefined / 4 | (After execution, the whole execution context will be deleted and the control goes back to the caller) | 
| ans : undefined / 4 / 16 | |
| square4 : undefined / 16 | | 


After the full execution, the global execution context is deleted. It was created in 2 phases: <b>Memory creation</b> and <b>Code Execution</b> and after the work is done it is deleted.

# Call Stack

There is a call stack in JS and in the call stack we have a the GEC and when a function is invoked or a new EC is created, it is pushed inside the stack and after it's execution, the EC is popped.
Finally after the whole code is executed, GEC is also popped out of the call stack.

`Call Stack maintains the order of execution of execution contexts`

- Call Stack (also called-)
- Execution Context Stack
- Program Stack
- Control Stack
- Runtime Stack
- Machine Stack