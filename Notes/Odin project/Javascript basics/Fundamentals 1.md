# numbers

### Binary , unary, operand
- Before we move on, let’s grasp some common terminology.

- _An operand_ – is what operators are applied to. For instance, in the multiplication of `5 * 2` there are two operands: the left operand is `5` and the right operand is `2`. Sometimes, people call these “arguments” instead of “operands”.
- An operator is _unary_ if it has a single operand. For example, the unary negation `-` reverses the sign of a number:
    `let x = 1;  _x = -x;_ alert( x ); // -1, unary negation was applied`
- An operator is _binary_ if it has two operands. The same minus exists in binary form as well:   `let x = 1, y = 3; alert( y - x ); // 2, binary minus subtracts values` Formally, in the examples above we have two different operators that share the same symbol: the negation operator, a unary operator that reverses the sign, and the subtraction operator, a binary operator that subtracts one number from another.

### Exponentials
- The exponentiation operator `a ** b` raises `a` to the power of `b`

### String concatenation with binary +
- Let’s meet the features of JavaScript operators that are beyond school arithmetic.
- Usually, the plus operator `+` sums numbers.
- But, if the binary `+` is applied to strings, it merges (concatenates) them: `let s = "my" + "string"; alert(s); // mystring`
- Note that if any of the operands is a string, then the other one is converted to a string too.
- For example: `alert( '1' + 2 ); // "12" alert( 2 + '1' ); // "21"`
- See, it doesn’t matter whether the first operand is a string or the second one.
- Here’s a more complex example: `alert(2 + 2 + '1' ); // "41" and not "221"`
- Here, operators work one after another. The first `+` sums two numbers, so it returns `4`, then the next `+` adds the string `1` to it, so it’s like `4 + '1' = '41'`.
- `alert('1' + 2 + 2); // "122" and not "14"`
- Here, the first operand is a string, the compiler treats the other two operands as strings too. The `2` gets concatenated to `'1'`, so it’s like `'1' + 2 = "12"` and `"12" + 2 = "122"`.
- The binary `+` is the only operator that supports strings in such a way. Other arithmetic operators work only with numbers and always convert their operands to numbers.
- Here’s the demo for subtraction and division: `alert( 6 - '2' ); // 4, converts '2' to a number alert( '6' / '2' ); // 3, converts both operands to numbers`

### Numeric conversion, unary +
- + can be used before a string to convert it into number 
- `let a = "2"`  here using `+a` convert the string into number
- `prompt("First number", 2`) here the prompt takes  a string . so you can use + to convert return value to int. `+prompt("First number", 3)`

### Chained assignment 
- `a = b = c = 2+2` here to variable a,b,c value of 4 is given

### Modify in place
- `n=n*1` can be writted as `n*=1` , `n=n+1` can be written as `n+=1`

### Increment/Decrement
- The operators `++` and `--` can be placed either before or after a variable.
- When the operator goes after the variable, it is in “postfix form”: `counter++`.
- The “prefix form” is when the operator goes before the variable: `++counter`.
- Both of these statements do the same thing: increase `counter` by `1`.
- Is there any difference? Yes, but we can only see it if we use the returned value of `++/--`.
- Let’s clarify. As we know, all operators return a value. Increment/decrement is no exception. The prefix form returns the new value while the postfix form returns the old value (prior to increment/decrement).
- To see the difference, here’s an example: `let counter = 1; let a = ++counter; // (*)  alert(a); // _2_`
- In the line `(*)`, the _prefix_ form `++counter` increments `counter` and returns the new value, `2`. So, the `alert` shows `2`.
- Now, let’s use the postfix form: `let counter = 1; let a = counter++; // (*) changed ++counter to counter++  alert(a); // _1_`
- In the line `(*)`, the _postfix_ form `counter++` also increments `counter` but returns the _old_ value (prior to increment). So, the `alert` shows `1`.

### Bitwise operators
- Bitwise operators treat arguments as 32-bit integer numbers and work on the level of their binary representation.
- These operators are not JavaScript-specific. They are supported in most programming languages.
- The list of operators:
	- AND ( `&` )
	- OR ( `|` )
	- XOR ( `^` )
	- NOT ( `~` )
	- LEFT SHIFT ( `<<` )
	- RIGHT SHIFT ( `>>` )
	- ZERO-FILL RIGHT SHIFT ( `>>>` )

### Comma
- The comma operator `,` is one of the rarest and most unusual operators. Sometimes, it’s used to write shorter code, so we need to know it in order to understand what’s going on.
- The comma operator allows us to evaluate several expressions, dividing them with a comma `,`. Each of them is evaluated but only the result of the last one is returned.
- ```javascriptlet a = (1 + 2, 3 + 4); alert( a ); // 7 (the result of 3 + 4)
```  Here, the first expression `1 + 2` is evaluated and its result is thrown away. Then, `3 + 4` is evaluated and returned as the result.
