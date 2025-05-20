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



### ✅ What is a Promise?

A **Promise** is a JavaScript object that represents the eventual **completion (or failure)** of an asynchronous operation and its resulting value.

### 📦 Promise States

A Promise has **three states**:

1. **Pending** – Initial state, neither fulfilled nor rejected.
    
2. **Fulfilled** – Operation completed successfully.
    
3. **Rejected** – Operation failed.
    

---

### ✍️ Creating a Promise

```js
const promise = new Promise((resolve, reject) => {
  // async operation
  if (success) {
    resolve(value); // success case
  } else {
    reject(error);  // failure case
  }
});
```

---

### 🔁 Consuming Promises

```js
promise
  .then(result => {
    // handle success
  })
  .catch(error => {
    // handle error
  })
  .finally(() => {
    // always runs (cleanup)
  });
```

---

### 🧱 Chaining Promises

```js
doTask1()
  .then(result1 => doTask2(result1))
  .then(result2 => doTask3(result2))
  .catch(error => handleError(error));
```

- Each `.then()` returns a new Promise.
    
- Useful for running async tasks in **sequence**.
    

---

### 🛠 Static Methods

#### `Promise.resolve(value)`

Returns a promise resolved with the given value.

```js
Promise.resolve(5).then(console.log); // 5
```

#### `Promise.reject(error)`

Returns a promise rejected with the given error.

```js
Promise.reject("Error").catch(console.error); // Error
```

#### `Promise.all([p1, p2, ...])`

Waits for **all** promises to resolve (or rejects on the first error).

```js
Promise.all([p1, p2])
  .then(([r1, r2]) => ...)
  .catch(err => ...);
```

#### `Promise.race([p1, p2, ...])`

Resolves or rejects as soon as **one** promise settles.

#### `Promise.allSettled([p1, p2, ...])`

Waits for **all** to settle, regardless of outcome.

---

### 🧠 Why Use Promises?

- Fix **inversion of control** (vs callbacks)
    
- Better **error handling**
    
- Support **chaining** of async operations
    
- Cleaner and **more readable code**
    

---

### 🆚 Promises vs Callbacks

|Feature|Callbacks|Promises|
|---|---|---|
|Control|External|You control `.then()`|
|Error Handling|Manual|Built-in `.catch()`|
|Nesting|Deep (callback hell)|Flat chaining|
|Composability|Hard|Easy with `.all()`, etc|

---

### 🧪 Example

```js
function getData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Done!"), 1000);
  });
}

getData()
  .then(data => console.log(data))
  .catch(err => console.error(err))
  .finally(() => console.log("Finished"));
```


In JavaScript, **Promises** help solve the **Inversion of Control (IoC)** problem that arises with **callbacks**, especially in asynchronous code. Here's a breakdown:

### 🔄 What is Inversion of Control (IoC)?

In **callback-based code**, **you give control to someone else** (like a library or API) by passing a callback. You trust that they’ll call it correctly and only once. But that’s risky.

**Example (callback style):**

```js
function getData(callback) {
  // Asynchronous call
  setTimeout(() => {
    // The library decides when and how to call your function
    callback('data from server');
  }, 1000);
}
```

You are **not in control**. If:

- the callback is called **multiple times**,
    
- called with **wrong arguments**,
    
- or **never called** — you’re stuck.
    

That’s **inversion of control**.

---

### ✅ How Promises "Uninvert" the Control

With Promises, instead of **passing a function into another function**, you get back a Promise object, and **you decide what to do with it**.

**Example (promise style):**

```js
function getData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('data from server');
    }, 1000);
  });
}

getData()
  .then(data => {
    console.log(data);
  })
  .catch(err => {
    console.error(err);
  });
```

- You **own the control flow**: `then`, `catch`, and `finally` are under your control.
    
- Promises guarantee:
    
    - Callback is called **once**.
        
    - It is **queued asynchronously** (avoiding sync surprises).
        
    - You can **chain** multiple `.then()` calls — clean flow.
        
    - Errors are **propagated** properly via `.catch()`.
        

---

### 🔑 Summary

**Promises uninvert control** by:

- Returning an object you can use (`Promise`) instead of giving away a callback.
    
- Making async flows more **predictable**, **composable**, and **trustworthy**.
    
- Avoiding "callback hell" and chaotic error handling.




### 🔄 Inversion of Control — Why Promises Fix It


### 🤔 What is _Inversion of Control_?

When using **callbacks**, you give _control_ of your function to someone else — they decide **when**, **how**, or even **if** your callback will be called. That’s risky.

You **lose control** over:

- When it runs
    
- How often it runs
    
- Whether errors are handled
    
- If it even gets called at all
    

---

### 🧨 Problem: Callback Misuse (Inversion of Control)

Let’s say you're using a 3rd-party library function:

```js
function getUserData(callback) {
  // Simulated external code
  setTimeout(() => {
    callback("user1");
    callback("user2"); // Oops! Called twice!
  }, 1000);
}

getUserData((user) => {
  console.log("Received:", user);
});
```

**What’s wrong?**

- The library called your callback **twice**
    
- Your app wasn’t ready for that!
    
- You can't prevent or control it
    

---

### ✅ Solution: Promise Gives _You_ the Control

Now the same logic using Promises:

```js
function getUserData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("user1");
      // resolve("user2"); ❌ This will be ignored if already resolved
    }, 1000);
  });
}

getUserData()
  .then(user => {
    console.log("Received:", user);
  })
  .catch(err => {
    console.error("Error:", err);
  });
```

**Why this is better:**

- `resolve()` or `reject()` can only be called **once**
    
- Any additional calls are **ignored silently**
    
- Your `.then()` will only run once, **predictably**
    
- You’re now in control of _how_ to handle it
    

---

### 🎯 Summary — Why Promises Fix Inversion of Control

|With Callbacks|With Promises|
|---|---|
|You pass your function into theirs|You handle the result from theirs|
|They call you back|You `.then()` when _you_ want|
|They might misuse your callback|Promises are automatically safe|
|Risk of duplicate or missed calls|Only one resolution allowed|
|You rely on _their_ error handling|Promises auto-capture errors|

---

### 🧠 Analogy

**Callback**: You hand over your keys to a stranger and _hope_ they return your car correctly.

**Promise**: You set up a valet stand — the driver gives you a ticket, and you control when to pick up the car. If something goes wrong, the system notifies you.

### PSET (creating program so that flow control can be of arbitrary length)

```js
function fakeAjax(url,cb) {
	var fake_responses = {
		"file1": "The first text",
		"file2": "The middle text",
		"file3": "The last text"
	};
	var randomDelay = (Math.round(Math.random() * 1E4) % 8000) + 1000;

	console.log("Requesting: " + url);

	setTimeout(function(){
		cb(fake_responses[url]);
	},randomDelay);
}

function output(text) {
	console.log(text);
}

// **************************************
// The old-n-busted callback way

function getFile(file) {
	return new Promise(function(resolve){
		fakeAjax(file,resolve);
	});
}

// Request all files at once in
// "parallel" via `getFile(..)`.
//
// Render as each one finishes,
// but only once previous rendering
// is done.

// ???
const req = ["file1", "file2", "file3"];
req.map(getFile).reduce(function combine(chain,promise) {
    return chain.then(function() {
        return promise;
    }).then(output);

},Promise.resolve())
```


## Promise.all()

### ✅ Purpose:

`Promise.all()` runs **multiple promises in parallel** and waits for **all of them to finish** (successfully).

---

## 📌 Syntax

```js
Promise.all([promise1, promise2, promise3])
  .then(results => {
    // All promises resolved
  })
  .catch(error => {
    // One of them failed
  });
```

---

## 🎯 Key Points

|Feature|Description|
|---|---|
|Input|An array of Promises|
|Resolves When|All promises are resolved|
|Returns|A single Promise that resolves to an array of results|
|Rejects When|**Any one** promise rejects (fails)|
|Execution Type|Promises run in **parallel**, not one-by-one|

---

## ✅ Example 1: All Promises Resolve

```js
const p1 = Promise.resolve(1);
const p2 = Promise.resolve(2);
const p3 = Promise.resolve(3);

Promise.all([p1, p2, p3]).then(results => {
  console.log(results); // [1, 2, 3]
});
```

---

## ❌ Example 2: One Promise Rejects

```js
const p1 = Promise.resolve(1);
const p2 = Promise.reject("Error in p2");
const p3 = Promise.resolve(3);

Promise.all([p1, p2, p3])
  .then(results => {
    // This won't run
  })
  .catch(err => {
    console.error(err); // "Error in p2"
  });
```

> 🔥 If **any** one promise fails, the whole `Promise.all()` fails immediately.

---

## ⚙️ Practical Example: Fetch Multiple Files

```js
function getFile(name) {
  return new Promise(resolve => {
    setTimeout(() => resolve(`Content of ${name}`), 1000);
  });
}

const req = ["file1", "file2", "file3"];
const promises = req.map(getFile);

Promise.all(promises).then(allContents => {
  console.log(allContents); 
  // ["Content of file1", "Content of file2", "Content of file3"]
});
```

---

## 🛑 When **NOT** to use `Promise.all()`

Use `.reduce()` or `for await` if:

- You need **sequential** (one-by-one) execution
    
- You want to handle failures individually
    

---

## 🧠 Quick Analogy

- `Promise.all()` is like waiting for **all food deliveries** to arrive before you eat.
    
- If **one** delivery fails — your entire dinner is canceled 🍽️❌
    
## 🚀 `Promise.race()` — Overview

### ✅ Purpose:

`Promise.race()` runs multiple promises in parallel and **settles (resolves or rejects)** as soon as **the first one finishes** — whether it's a **success** or an **error**.

---

## 📌 Syntax

```js
Promise.race([promise1, promise2, promise3])
  .then(result => {
    // First promise resolved
  })
  .catch(error => {
    // First promise rejected
  });
```

---

## 🎯 Key Features

|Feature|Description|
|---|---|
|Input|Array of Promises|
|Resolves/Rejects On|**First settled promise** (the earliest to finish — success or error)|
|Returns|A single Promise with the result of the first settled one|
|Use Case|Timeouts, choosing the fastest, fallback options|

---

## ✅ Example 1: Fastest Wins

```js
const fast = new Promise(resolve => setTimeout(() => resolve("Fast"), 100));
const slow = new Promise(resolve => setTimeout(() => resolve("Slow"), 500));

Promise.race([fast, slow])
  .then(result => console.log(result));  // Output: "Fast"
```

---

## ❌ Example 2: First is Error

```js
const failQuick = new Promise((_, reject) => setTimeout(() => reject("Failed fast"), 100));
const succeedSlow = new Promise(resolve => setTimeout(() => resolve("Success"), 500));

Promise.race([failQuick, succeedSlow])
  .catch(error => console.log(error));  // Output: "Failed fast"
```

> ⚠️ If the **first one fails**, the whole race fails immediately.

---

## ⏱️ Example 3: Timeout Pattern

```js
function fetchWithTimeout(fetchPromise, ms) {
  const timeout = new Promise((_, reject) =>
    setTimeout(() => reject("Timeout!"), ms)
  );
  return Promise.race([fetchPromise, timeout]);
}

// Simulated slow fetch
const slowFetch = new Promise(resolve =>
  setTimeout(() => resolve("Data from server"), 2000)
);

fetchWithTimeout(slowFetch, 1000)
  .then(console.log)
  .catch(console.error); // Output: "Timeout!"
```

---

## 🔍 Summary Comparison

|Feature|`Promise.all()`|`Promise.race()`|
|---|---|---|
|Waits for|All promises|First to settle|
|Fails if|Any one fails|First to reject|
|Result|Array of results|Single result (first settled)|

---

## 🧠 Analogy

> Think of `Promise.race()` like a **horse race** — the first horse to finish determines the outcome 🐎

## Generators(Yield)
- Once a piece of synchronous JavaScript code starts executing, it **runs all the way to the end** before anything else (like events, timers, or other code) can run.
- Generators in JavaScript are **pauseable functions**. They allow execution to be **suspended** and **resumed**, which means they **don’t run to completion in one go**
- Generator is a syntatic form of a state machine
- When you write a generator function, you're **implicitly** writing a **state machine** — a program that can pause and resume between multiple states.
- Here the blocking is happening only inside the generator but not the outside world program

```js
function* myGenerator() {
  console.log("Step 1");
  yield;
  console.log("Step 2");
}

const gen = myGenerator();
gen.next();  // logs: Step 1
gen.next();  // logs: Step 2
```
yield is the pause button
- executing a generator does not run the function but it produce a iterator 
- here the purpose is not to step data but to step thru control of our generator from outside

## 🧠 Concept: Messaging in Generators

- You can **pass a value into a generator** using `next(value)`.
    
- That value is **received by the generator at the `yield` expression**.
    

---

## ✅ Example: Sending Data Into a Generator

```js
function* messenger() {
  const name = yield "What's your name?";
  console.log(`Hello, ${name}!`);
}

const gen = messenger();

console.log(gen.next().value);     // Output: What's your name?
gen.next("Alice");                 // Logs: Hello, Alice!
```

### 🔍 What’s Happening?

1. First `next()` runs until `yield "What's your name?"`
    
2. That `yield` pauses and **returns** `"What's your name?"`
    
3. Then, we call `next("Alice")`
    
    - `"Alice"` becomes the **result of the yield expression**
        
    - `const name = yield ...` now gets `"Alice"`
        

---

## 💡 Summary Table

|Call|Generator Line|Effect|
|---|---|---|
|`gen.next()`|Runs to first `yield`|Yields a prompt|
|`gen.next("Alice")`|Injects "Alice" into `yield`|Assigns it to `name`|

---

## 🧠 Messaging is a Two-Way Street

- `yield` gives a value **out**
    
- `next()` sends a value **in**
    

So you can treat generators like **coroutines** or **data-exchanging state machines**.

---

## 🔄 Example: Generator that Accumulates Inputs

```js
function* adder() {
  let sum = 0;
  while (true) {
    const num = yield sum;
    sum += num;
  }
}

const gen = adder();
console.log(gen.next().value);     // 0 (initial sum)
console.log(gen.next(5).value);    // 5
console.log(gen.next(10).value);   // 15
console.log(gen.next(2).value);    // 17
```

---

## ✅ Use Cases

- Async task control
    
- Custom iterators with dynamic input
    
- Controlled state machines
    
- Middleware pipelines
    

## 🔁 `gen.next(value)` returns:

```js
{ value: ..., done: ... }
```

|Property|Meaning|
|---|---|
|`value`|The result from the current `yield` or `return`|
|`done`|`false` if the generator has more code to run; `true` if it’s finished (i.e., hit `return` or the end of the function)|

---

## 🔍 Example: See `value` and `done` in Action

```js
function* greeter() {
  const name = yield "What's your name?";
  yield `Hello, ${name}!`;
  return "Bye!";
}

const gen = greeter();

console.log(gen.next());        // { value: "What's your name?", done: false }
console.log(gen.next("Alice")); // { value: "Hello, Alice!", done: false }
console.log(gen.next());        // { value: "Bye!", done: true }
console.log(gen.next());        // { value: undefined, done: true }
```

---

## 🧠 Explanation:

|Step|Call|Returned `{ value, done }`|What's happening|
|---|---|---|---|
|1|`gen.next()`|`{ value: "What's your name?", done: false }`|Execution pauses at first `yield`|
|2|`gen.next("Alice")`|`{ value: "Hello, Alice!", done: false }`|`"Alice"` is passed into `yield`, returned message|
|3|`gen.next()`|`{ value: "Bye!", done: true }`|Generator hits `return`|
|4|`gen.next()`|`{ value: undefined, done: true }`|Already completed, so stays done|

---

## 💡 Note:

Once `done: true`, **the generator cannot be restarted**. You'd have to create a new instance with `greeter()`.
