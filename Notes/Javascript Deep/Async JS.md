## Single threaded JS

### Parallel vs Async 
### Event loop

## Callbacks
A **callback** is a function that is passed as an argument to another function and is executed later when a certain event or task is completed.

### Callback hell
![](../statics/Pasted%20image%2020250313212716.png)
- callback hell does not have anything to do with nesting or indentation
![](../statics/Pasted%20image%2020250313212853.png)
### Inversion of control
- Half of control to us and other half not in control , for example first half execute now and second half as callback  which is user by some other
- But there is a trust issue what if callback gets called multiple times 
- ![](../statics/Pasted%20image%2020250314081224.png)
- **Temporal dependency** refers to a situation where the execution or outcome of one operation depends on the timing or order of another operation.
- Only way to express temporal dependency is thru nesting them in callbacks

### Thunks 
- ![](../statics/Pasted%20image%2020250314121118.png)
- Sync Thunk: It is a function that has already it needs to do to give some value back
- Async Thunk:- Function that does not need any argument passed to it to do its job except callback
- ![](../statics/Pasted%20image%2020250314121055.png)


## Promises
- It is an object representing eventual completion or failure of async operation

![](../statics/Pasted%20image%2020250315090124.png)
