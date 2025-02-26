## Types
- Everything in JS is not an object , they behave as obj but not an obj
- There are primitive datatype in JS 
	- Undefined
	- string
	- number 
	- boolean 
	- object
	- bigint
	- symbols
- Array and function are subtype of object type
- What is a type:- set of intrinsic charactersitics that we will be able to do with that value
- When we are using `typeof` we are looking what is the type of value that is in a variable not what is type of variable
- undefined does not implies it does not have a value yet , but it means it does not currently have a value. 

### Null giving Object as type 
The reason `typeof null` returns `"object"` in JavaScript is **due to a historical bug in the language that was never fixed for backward compatibility**.

**How `typeof` Works Internally**
- JavaScript stores values using **binary representations**.
- In early implementations, JavaScript used a **tagged representation** where the **lower bits of a value** indicated its type.
- Objects had a **type tag of `000`**, and `null` was mistakenly given the same **binary representation** as objects.

### BigInt
![](../statics/Pasted%20image%2020250226120640.png)
### Undefined vs Undeclared
- Undeclared: - it means it has never been created in any scope we have access to
- Undefined:- There is a variable that currently does not have a value.
- Typeof opertaor is only where it does not throw error if it reference which does not exist


### NaN & isNaN
- NaN does not essentialy means not a number but invalid number
- ![](../statics/Pasted%20image%2020250226121210.png)
- at line 4 it is returning NaN because for - we need number so it tries to turn it into a number and it fails so return NaN
- at line 6 it is false because NaN is not equal to each other
- at line 10 it return true because isNaN first tries to turn value to number and it return NaN so true
- `Number.isNaN` does not do that

### Negative Zero
- ![](../statics/Pasted%20image%2020250226121725.png)
- ![](../statics/Pasted%20image%2020250226121956.png)
- 