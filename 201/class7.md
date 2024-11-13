# Reading Notes: Object-Oriented Programming (OOP) and HTML Tables

## Why This Topic Matters

Understanding **Object-Oriented Programming (OOP)** principles, especially **constructors** and **prototypes**, is fundamental for building scalable, efficient, and organized code. Similarly, learning **HTML tables** helps in effectively displaying tabular data on webpages, which is essential in web development.

---

## Domain Modeling

### Why We Need Domain Modeling

Domain modeling is essential because it helps developers visually map out the **relationships between entities in a system**, guiding the logical structure of the code. This is especially useful in complex applications, as it clarifies how data flows and interacts across the app.

---

## HTML Table Basics

### Why Not to Use Tables for Page Layouts

Tables are not recommended for page layouts because they create a rigid structure that makes responsiveness and accessibility more difficult. Layouts should ideally use **CSS for flexible and accessible designs**.

### 3 Semantic HTML Elements in `<table>`

- `<thead>`: Groups the header content in a table, enhancing readability and accessibility.
- `<tbody>`: Organizes the main data within the table, creating a clear distinction between header and content.
- `<tfoot>`: Defines the footer of the table, allowing for summary data, like totals, to be separate from main data entries.

---

## Introducing Constructors

### What Is a Constructor and Its Advantages

A constructor in JavaScript is a **special function used to create and initialize objects**. Constructors allow for the creation of multiple instances of an object with a similar structure, providing code efficiency and modularity.

### Differences in Using `this`

- **Object Literal**: `this` refers to the current instance of the object being created.
- **Constructor**: `this` refers to the specific instance created by the constructor, meaning each new instance of an object has unique properties and values assigned to `this`.

---

## Object Prototypes Using a Constructor

### Prototypes and Inheritance Analogy

Think of prototypes as a "base template" that can be used to create new instances. In the medical field, it’s like using a **standardized patient record template** (prototype) that is customized (inherited) for each patient instance, yet retains access to core data fields (properties and methods) common across all records.

---

#### **Constructor Function**

A  **constructor function**  in JavaScript is a function used to create and initialize new objects. It is invoked using the  `new`  keyword and allows multiple instances of similar objects to be created with their own properties and methods. Each instance of the object has access to properties defined within the constructor function.

**Key points:**

-   A constructor function is typically defined with a capitalized name (e.g.,  `Person`), following the  **camelCase**  convention.
-   The  `this`  keyword is used inside the constructor to assign values to properties of the newly created object.
-   When invoked with the  `new`  keyword, it creates a new instance of the object, and  `this`  refers to that instance.

**Example:**

``function Person(name, age) {
  this.name = name;
  this.age = age;
  this.sayHello = function() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  };
}

const person1 = new Person('John', 30);
person1.sayHello();  // "Hello, my name is John and I am 30 years old."`` 

In the above example:

-   The  `Person`  function is a constructor that creates new  `Person`  objects with  `name`  and  `age`  properties.
-   The  `sayHello`  method is also attached to each  `Person`  object.
-   Using  `new Person('John', 30)`  creates a new  `Person`  instance with the specified properties.

----------

#### **How  `this`  Works in Object Literals vs Constructor Functions**

The behavior of  `this`  differs when referencing objects defined via  **object literals**  and those created with a  **constructor function**.

1.  **In Object Literals**:
    
    -   `this`  refers to the object itself when used within an object literal.
    -   Object literals are simple and define key-value pairs directly within  `{}`.
    
    **Example:**
    
    ``const person = {
      name: 'Jane',
      age: 25,
      sayHello: function() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
      }
    };
    person.sayHello();  // "Hello, my name is Jane and I am 25 years old."`` 
    
    Here,  `this`  in the  `sayHello`  function refers to the  `person`  object, which contains the  `name`  and  `age`  properties.
    
2.  **In Constructor Functions**:
    
    -   `this`  refers to the instance of the object being created by the constructor.
    -   Each new object created with the constructor gets its own set of properties.
    
    **Example:**
    
    
    `function Person(name, age) {
      this.name = name;
      this.age = age;
    }
    
    const person2 = new Person('Alice', 28);
    console.log(person2.name);  // "Alice"` 
    
    Here,  `this`  inside the  `Person`  constructor refers to the newly created object,  `person2`. Each time the constructor is invoked with  `new`, a new object is created, and  `this`  is used to define its properties.
    

----------

#### **HTML Elements That Make Up an HTML Table**

HTML tables are structured using several key elements that define the layout and organization of the data. The main elements are:

1.  **`<table>`**: The container element that holds the entire table structure.
2.  **`<tr>`**  (Table Row): Defines a row of cells within the table, containing either headers or data cells.
3.  **`<th>`**  (Table Header): Defines a header cell, which is typically bold and centered, used to label columns or rows.
4.  **`<td>`**  (Table Data): Represents the data cell in the table, where actual content is placed.
5.  **`<thead>`**  (Table Head): Groups the header content of the table, typically wrapping  `<tr>`  elements containing  `<th>`  tags.
6.  **`<tbody>`**  (Table Body): Groups the main data content of the table, typically wrapping  `<tr>`  elements containing  `<td>`  tags.
7.  **`<tfoot>`**  (Table Footer): Groups the footer content of the table, often used for summary rows or footer notes.

**Example of a basic HTML table structure:**\

`<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>30</td>
    </tr>
    <tr>
      <td>Jane</td>
      <td>25</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Table footer</td>
    </tr>
  </tfoot>
</table>` 

- **`<thead>`**  contains column headers, defined by  `<th>`.
- **`<tbody>`**  contains the main content of the table, organized in rows and columns.
- **`<tfoot>`**  contains footer data, often used for summary or other end-of-table information.

This structure helps make the data both semantically correct and easy to style with CSS.

## Things I Want to Know More About

- How can constructors and prototypes be extended for complex data structures?
- What are best practices for enhancing table accessibility in HTML?
- How does `this` behave differently in strict mode?

