- A `ReferenceError` is thrown when one refers to a variable that is not declared and/or initialized within the current scope.
- Another important part of an error is the stack trace. This helps you understand when the error was thrown in your application, and what functions were called that led up to the error. So, for example, if we have the following code:
- ![](../../statics/Pasted%20image%2020230614071504.png )
- Our function `print()` should call on `add()`, which returns a variable named `c`, which currently has not been declared. The corresponding error is as follows:
- ![](../../statics/Pasted%20image%2020230614071534.png )
- The stack trace tells us that:
	1. `c is not defined` in scope of `add()`, which is declared on line 5
	2. `add()` was called by `print()`, which was declared on line 9
	3. `print()` itself was called on line 12.
- Thus the stack trace lets you trace the evolution of an error back to its origin, which here is the declaration of `add()`.
-  Syntax Error: A syntax error occurs when the code you are trying to run is not written correctly, i.e., in accordance with the grammatical rules of JavaScript. 
-  Type Error These errors are thrown for a few different reasons: Per MDN, a `TypeError` may be thrown when:
 - an operand or argument passed to a function is incompatible with the type expected by that operator or function;
 - or when attempting to modify a value that cannot be changed;
 - or when attempting to use a value in an inappropriate way.
 - Lastly, many people are met with warnings and treat them as errors. Errors will stop the execution of your program or whatever process you may be attempting to run and prevent further action. Warnings, on the other hand, are messages that provide you insight on potential problems that may not necessarily crash your program at runtime, or at all! While you should address these warnings if possible and as soon as possible, warnings are not as significant as errors and are more likely to be informational. Warnings are typically shown in yellow, while errors are typically shown in red. Though these colors are not a rule, frequently there will be a visual differentiation between the two, regardless of the platform you are encountering them on.
 - 
