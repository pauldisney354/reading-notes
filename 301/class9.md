## 📚 Functional Programming & Node.js Modules – Reading Notes

### Why This Topic Matters

In this module, we're learning how to write cleaner, modular, and more maintainable JavaScript code. **Functional Programming** teaches us to write predictable, testable code by embracing immutability and pure functions, while **Node.js modules** allow us to structure our code into reusable parts. Together, these concepts help build scalable applications that are easier to debug and reason about.

----------

### 🧠 Functional Programming Concepts

#### What is functional programming?

Functional programming is a programming style centered on **pure functions**, **immutability**, and **function composition**. It emphasizes writing declarative code—focusing on _what_ needs to be done, rather than _how_ to do it.

#### What is a pure function and how do we know if something is a pure function?

A **pure function**:

-   Always returns the same result given the same inputs.
    
-   Does **not** modify any external state or cause side effects (like logging or changing variables outside its scope).
    

**Example (pure):**

```js
const square = x => x * x;

```

**Example (impure):**

```js
let counter = 0;
function increment() {
  counter++;
}

```

#### What are the benefits of a pure function?

-   ✅ Easy to test and debug
    
-   🔁 Reusable and composable
    
-   📚 Makes code more readable
    
-   🧪 Great for unit testing
    
-   ⚙️ Helps prevent unexpected side effects
    

#### What is immutability?

**Immutability** means that once a value is created, it cannot be changed. Instead of altering data, new values are returned with the updated state.

**Example:**

```js
const user = { name: "Paul", age: 30 };
const updatedUser = { ...user, age: 31 };

```

Benefits include:

-   More predictable code
    
-   Fewer bugs from unexpected changes
    
-   Supports functional programming principles
    

#### What is Referential Transparency?

A code expression is **referentially transparent** if you can replace it with its value **without affecting the result** of the program.

**Example:**

```js
const x = 4 + 4; // x will always be 8

```

Referential transparency makes code easier to:

-   Optimize
    
-   Test
    
-   Understand
    

----------

### 📦 Node.js Modules and `require()`

#### What is a module?

A **module** is a reusable chunk of code that encapsulates functions, variables, or classes. In Node.js, each file is treated as its own module.

#### What does the word ‘require’ do?

`require()` is a built-in function in Node.js that:

-   Loads a module
    
-   Executes it once
    
-   Returns its `exports` so they can be used in other files
    

#### How do we bring another module into the file we are working in?

Use `require()` with a **relative path**:

```js
const math = require('./math');

```

#### What do we have to do to make a module available?

We export it using `module.exports`:

```js
// math.js
function add(a, b) {
  return a + b;
}
module.exports = { add };

```

----------

## 🔍 Things I Want to Know More About

-   Are there JavaScript libraries that make functional programming easier (like Ramda or Lodash/fp)?
    
-   What are the trade-offs between functional and object-oriented programming in real-world projects?
    
-   How does functional programming scale in large codebases?
    
-   What are best practices for organizing Node.js modules?
    

----------

### 📚 Sources

-   Code Fellows Curriculum (2025). _Functional Programming Concepts_.
    
-   The Net Ninja. (YouTube). _Node JS Tutorial for Beginners #6 - Modules and require()_.
    
-   MDN Web Docs – [Immutability](https://developer.mozilla.org/en-US/docs/Glossary/Immutable)
    
-   [JavaScript.info on Modules](https://javascript.info/modules-intro)

----------

### 💡 DRY Code (Don't Repeat Yourself)

**DRY** means: avoid repeating logic, patterns, or code blocks. Instead, **encapsulate** repeated behavior into **functions, modules, or components**.

👎 Bad (repetition):

```js
fetch('/users').then(...);
fetch('/posts').then(...);

```

👍 DRY:

```js
function fetchData(endpoint) {
  return fetch(endpoint).then(res => res.json());
}

fetchData('/users');
fetchData('/posts');

```

✅ Benefits:

-   Easier to debug and maintain
    
-   Reduces chance of errors from copy/pasting
    
-   Encourages modular thinking and reuse
    

----------

### 🧱 Why Do We Modularize Code?

**Modularization** breaks code into **small, reusable, isolated units**. In Node.js, this is typically done using `module.exports`.

✅ Benefits:

-   Improves **readability**
    
-   Encourages **reusability** and **separation of concerns**
    
-   Makes **testing** easier
    
-   Helps with **team collaboration**
    

#### Example

**📁 doSomething.js**

```js
function doSomething() {
  console.log("Doing something cool!");
}
module.exports = doSomething;

```

**📁 server.js**

```js
const doSomething = require('./doSomething');
doSomething(); // logs: Doing something cool!

```

✅ You can also export multiple functions:

```js
module.exports = {
  doSomething,
  doSomethingElse
};

```

----------

### 🔄 What Is a Promise?

A **Promise** is an object representing the eventual **completion** or **failure** of an asynchronous operation.

```js
const promise = new Promise((resolve, reject) => {
  // async logic
});

```

It has **three states**:

-   `pending`
    
-   `fulfilled` → `.then()`
    
-   `rejected` → `.catch()`
    

----------

### ⚖️ Difference: Promise vs `.then()`/`.catch()`

A **Promise** is a data structure.

`.then()` and `.catch()` are **methods** used to handle **results or errors** when a Promise settles.

```js
// Creating a Promise
const myPromise = new Promise((resolve, reject) => {
  resolve('Success!');
});

// Using the Promise
myPromise
  .then(data => console.log(data))
  .catch(err => console.error(err));

```

----------

### 🆚 `async/await` vs `.then()`/`.catch()`

These both **consume** Promises, but the syntax and readability differ:

#### ✅ `async/await`

```js
async function fetchUser() {
  try {
    const response = await axios.get('/user');
    console.log(response.data);
  } catch (err) {
    console.error(err);
  }
}

```

#### ✅ `.then()`/`.catch()`

```js
function fetchUser() {
  axios
    .get('/user')
    .then(response => console.log(response.data))
    .catch(err => console.error(err));
}

```

### 🧠 Key Differences

Feature

`.then()/.catch()`

`async/await`

Style

Chained

Sequential

Error Handling

`.catch()` method

`try/catch` block

Readability

Harder with nested chains

Cleaner and easier to follow

When to Use

Simple async tasks, chaining multiple promises

Complex logic or control flow with `await`

----------

### 🧩 Summary of Server-Side Modularization

#### Exporting

```js
// Exporting a named function
function doSomething() {}
module.exports = doSomething;

// OR export an anonymous function
module.exports = () => {};

// Export multiple functions
module.exports = {
  doSomething,
  doSomethingElse
};

```

#### Importing

```js
const { doSomething, doSomethingElse } = require('./myModule');

```

Or if importing the whole object:

```js
const stuff = require('./myModule');
stuff.doSomething();
stuff.doSomethingElse();

```

----------

### 📚 List of Resources

-   📘 [MDN - Promises](https://www.google.com/search?q=MDN+JavaScript+Promises)
    
-   📘 [MDN - async/await](https://www.google.com/search?q=mdn+async+await)
    
-   📘 [Node.js Modules](https://www.google.com/search?q=node+js+module+exports+require+example)
    
-   🎓 [JavaScript.info - Promises](https://www.google.com/search?q=javascript+info+promises+then+catch+async+await)
    
-   🛠️ [Axios GitHub Repo](https://www.google.com/search?q=axios+github+repo+examples)
    

----------

### See also

-   🧠 [Clean Code Principles](https://www.google.com/search?q=clean+code+principles+in+javascript) – foundational software design best practices
    
-   📦 [CommonJS vs ES6 Modules](https://www.google.com/search?q=commonjs+vs+es6+modules+nodejs) – module systems comparison
    
-   🧪 [How to Unit Test Modular Functions](https://www.google.com/search?q=unit+testing+modular+functions+in+javascript) – for TDD fans

-   🐢 [Callback Hell Examples](https://www.google.com/search?q=callback+hell+examples+and+solutions) – why Promises were born
    
-   🔗 [Chaining Promises vs Async/Await](https://www.google.com/search?q=chaining+promises+vs+async+await) – visual flowcharts
    

----------