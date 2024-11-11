## JavaScript Objects and the DOM

### How would you describe an object to a non-technical friend?

An object is like a collection of details about something. Imagine describing your phone: it has a color, model, and brand. An object in programming is the same idea—it groups related information together.

### What are some advantages to creating object literals?

Object literals make it easy to organize related information and actions together in one place. They help keep code clear and save time by letting you create one-off objects without extra setup.

### How do objects differ from arrays?

Objects store data as named key-value pairs (like a list of traits with labels), while arrays store items in an ordered list, accessed by position. Use objects for labeled data and arrays for lists of items.

### When would you need to use bracket notation to access an object’s property instead of dot notation?

Use bracket notation if the property name has spaces, special characters, or is stored in a variable:

`const person = {
  "first name": "Alice"
};
console.log(person["first name"]); // Bracket notation needed because of the space` 

### What does `this` refer to in the code, and why is it useful?

``const dog = {
  name: 'Spot',
  age: 2,
  humanAge: function (){
    console.log(`${this.name} is ${this.age * 7} in human years`);
  }
}`` 

In this code, `this` refers to the `dog` object. It lets you access the object's own properties from within a method, making the code more flexible and reusable.

### What is the DOM?

The Document Object Model (DOM) represents a webpage’s structure as a tree of elements. It lets JavaScript interact with and change elements on the page.

### How does JavaScript use the DOM?

JavaScript uses the DOM to find and update parts of a webpage, like changing text or styles or adding new elements, to make the page interactive.

### What’s the difference between primitive values and object references in JavaScript?

Primitive values (like numbers and strings) store data directly. Object references (like objects and arrays) store a link to the data. Copying a primitive value copies its data, while copying an object reference only copies the link, so both variables point to the same object.