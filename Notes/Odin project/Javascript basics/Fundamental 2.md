# Strings
- However, you can't include the same quote mark inside the string if it's being used to contain them. The following will error, as it confuses the browser as to where the string ends:
```
const bigmouth = 'I've got no right to take my place…';
```

### Escaping character in a string
- Escaping characters means that we do something to them to make sure they are recognized as text, not part of the code. In JavaScript, we do this by putting a backslash just before the character. Try this:

```
const bigmouth = 'I\'ve got no right to take my place…'
```
### Concatenating string 
- Concatenate just means "join together". To join together strings in JavaScript you can use a different type of string, called a _template literal_.
- A template literal looks just like a normal string, but instead of using single or double quote marks (`'` or `"`), you use backtick characters (`` ` ``):
- you can include variables in it, wrapped inside `${ }` characters, and the variable's value will be inserted into the result:

```
const name = "Chris";
const greeting = `Hello, ${name}`;
console.log(greeting); // "Hello, Chris"
```
- You can use the same technique to join together two variables:

```
const one = "Hello, ";
const two = "how are you?";
const joined = `${one}${two}`;
console.log(joined); // "Hello, how are you?"
```
- The Number() function converts anything passed to it into a number, if it can. Try the following:
    ```
    const myString = "123";
    const myNum = Number(myString);
    console.log(typeof myNum);
    ``` 
- Conversely, every number has a method called `toString()` that converts it to the equivalent string. Try this:
    ```
    const myNum2 = 123;
    const myString2 = myNum2.toString();
    console.log(typeof myString2);
    ```
You can include JavaScript expressions in template literals, as well as simple variables, and the results will be included in the result:

```
const song = "Fight the Youth";
const score = 9;
const highestScore = 10;
const output = `I like the song ${song}. I gave it a score of ${
  (score / highestScore) * 100
}%.`;
console.log(output); // "I like the song Fight the Youth. I gave it a score of 90%."
```

# Conditionals

## Comparison
- In JavaScript they are written like this:
- Greater/less than: `a > b`, `a < b`.
- Greater/less than or equals: `a >= b`, `a <= b`.
- Equals: `a == b`, please note the double equality sign `==` means the equality test, while a single one `a = b` means an assignment.
- Not equals: In maths the notation is `≠`, but in JavaScript it’s written as `a != b`
- All comparison operators return a boolean value:
- `true` – means “yes”, “correct” or “the truth”.
- `false` – means “no”, “wrong” or “not the truth”.
### String comparison
- To see whether a string is greater than another, JavaScript uses the so-called “dictionary” or “lexicographical” order.
- In other words, strings are compared letter-by-letter.
- For example: `alert( 'Z' > 'A' ); // true alert( 'Glow' > 'Glee' ); // true alert( 'Bee' > 'Be' ); // true`
### Comparison of different type
- When comparing values of different types, JavaScript converts the values to numbers.
- For example: `alert( '2' > 1 ); // true, string '2' becomes a number 2 alert( '01' == 1 ); // true, string '01' becomes a number 1`
- For boolean values, `true` becomes `1` and `false` becomes `0`. 
- For example: `alert( true == 1 ); // true alert( false == 0 ); // true`
### Strict equality
- A regular equality check `==` has a problem. It cannot differentiate `0` from `false`: `alert( 0 == false ); // true` `alert( '' == false ); // true`
- This happens because operands of different types are converted to numbers by the equality operator `==`. An empty string, just like `false`, becomes a zero.
- What to do if we’d like to differentiate `0` from `false`?
- **A strict equality operator `===` checks the equality without type conversion.**
- In other words, if `a` and `b` are of different types, then `a === b` immediately returns `false` without an attempt to convert them.
- Let’s try it: `alert( 0 === false ); // false, because the types are different` There is also a “strict non-equality” operator `!==` analogous to `!=`.
- The strict equality operator is a bit longer to write, but makes it obvious what’s going on and leaves less room for errors.
- Treat any comparison with `undefined/null` except the strict equality `===` with exceptional care.
- Don’t use comparisons `>= > < <=` with a variable which may be `null/undefined`, unless you’re really sure of what you’re doing. If a variable can have these values, check for them separately

### Logical operators
- There are four logical operators in JavaScript: `||` (OR), `&&` (AND), `!` (NOT), `??` (Nullish Coalescing). Here we cover the first three, the `??` operator is in the next article.
#### || (OR)
- The logic described above is somewhat classical. Now, let’s bring in the “extra” features of JavaScript.
- The extended algorithm works as follows.
- Given multiple OR’ed values: `result = value1 || value2 || value3;`
- The OR `||` operator does the following:
	- Evaluates operands from left to right.
	- For each operand, converts it to boolean. If the result is `true`, stops and returns the original value of that operand.
	- If all operands have been evaluated (i.e. all were `false`), returns the last operand.
- A value is returned in its original form, without the conversion.
- In other words, a chain of OR `||` returns the first truthy value or the last one if no truthy value is found.

#### &&(and)
- Given multiple AND’ed values:`result = value1 && value2 && value3;`
- The AND `&&` operator does the following:
	- Evaluates operands from left to right.
	- For each operand, converts it to a boolean. If the result is `false`, stops and returns the original value of that operand.
	- If all operands have been evaluated (i.e. all were truthy), returns the last operand.
- In other words, AND returns the first falsy value or the last value if none were found.

#### ! (NOT)
- The boolean NOT operator is represented with an exclamation sign `!`.
- The syntax is pretty simple:`result = !value;`
- The operator accepts a single argument and does the following:
	1. Converts the operand to boolean type: `true/false`.
	2. Returns the inverse value.
- For instance:`alert( !true ); // false alert( !0 ); // true`
- A double NOT `!!` is sometimes used for converting a value to boolean type:
- `alert( !!"non-empty string" ); // true alert( !!null ); // false`
- That is, the first NOT converts the value to boolean and returns the inverse, and the second NOT inverses it again. In the end, we have a plain value-to-boolean conversion.
- There’s a little more verbose way to do the same thing – a built-in `Boolean` function:

## If and else
- We wanted to make a special mention of testing boolean (`true`/`false`) values, and a common pattern you'll come across again and again. Any value that is not `false`, `undefined`, `null`, `0`, `NaN`, or an empty string (`''`) actually returns `true` when tested as a conditional statement, therefore you can use a variable name on its own to test whether it is `true`, or even that it exists (that is, it is not undefined.) So for example:
```
let cheese = "Cheddar";

if (cheese) {
  console.log("Yay! Cheese available for making cheese on toast.");
} else {
  console.log("No cheese on toast for you today.");
}
```
- The last type of logical operator, NOT, expressed by the `!` operator, can be used to negate an expression. Let's combine it with OR in the above example:
```
if (!(iceCreamVanOutside || houseStatus === "on fire")) {
  console.log("Probably should just stay in then.");
} else {
  console.log("You should leave the house quickly.");
}
```
- In this snippet, if the OR statement returns `true`, the NOT operator will negate it so that the overall expression returns `false`.
- You can combine as many logical statements together as you want, in whatever structure. The following example executes the code inside only if both OR statements return true, meaning that the overall AND statement will return true:

## Switch statement
- In such a case, `switch` statements are your friend — they take a single expression/value as an input, and then look through several choices until they find one that matches that value, executing the corresponding code that goes along with it. Here's some more pseudocode, to give you an idea:
```
switch (expression) {
case choice1:
run this code
break;

case choice2:
run this code instead
break;

// include as many cases as you like

default:
actually, just run this code
}
```
Here we've got:
1. The keyword `switch`, followed by a set of parentheses.
2. An expression or value inside the parentheses.
3. The keyword `case`, followed by a choice that the expression/value could be, followed by a colon.
4. Some code to run if the choice matches the expression.
5. A `break` statement, followed by a semicolon. If the previous choice matches the expression/value, the browser stops executing the code block here, and moves on to any code that appears below the switch statement.
6. As many other cases (bullets 3–5) as you like.
7. The keyword `default`, followed by exactly the same code pattern as one of the cases (bullets 3–5), except that `default` does not have a choice after it, and you don't need the `break` statement as there is nothing to run after this in the block anyway. This is the default option that runs if none of the choices match.
## Ternary operator
- The **conditional (ternary) operator** is the only JavaScript operator that takes three operands: a condition followed by a question mark (`?`), then an expression to execute if the condition is truthy followed by a colon (`:`), and finally the expression to execute if the condition is falsy. This operator is frequently used as an alternative to an `if...else` statement.
```
condition ? exprIfTrue : exprIfFalse
```
### Parameters
- `condition` :An expression whose value is used as a condition.
- `exprIfTrue`: An expression which is executed if the `condition` evaluates to a truthy value (one which equals or can be converted to `true`).
- `exprIfFalse`: An expression which is executed if the `condition` is falsy (that is, has a value which can be converted to `false`).
- Besides `false`, possible falsy expressions are: `null`, `NaN`, `0`, the empty string (`""`), and `undefined`. If `condition` is any of these, the result of the conditional expression will be the result of executing the expression `exprIfFalse`.

