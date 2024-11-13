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

## Things I Want to Know More About

- How can constructors and prototypes be extended for complex data structures?
- What are best practices for enhancing table accessibility in HTML?
- How does `this` behave differently in strict mode?

