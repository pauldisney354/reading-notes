# **Node.js Reading Notes**  

## **Why This Topic Matters**
Node.js is a critical tool for modern web development, allowing JavaScript to run outside the browser. Understanding how it works helps in building backend applications, working with APIs, and managing packages effectively.

---

## **Reading Questions and Answers**

### **Node.js Basics**
1. **What is Node.js?**  
   Node.js is an open-source, server-side runtime that allows JavaScript to be executed outside the browser. It is widely used for backend development and is known for its non-blocking, event-driven architecture.

2. **What is Chrome’s V8 JavaScript Engine?**  
   Chrome’s V8 Engine is Google’s high-performance JavaScript engine that compiles JavaScript into machine code for faster execution. It powers both Chrome and Node.js.

3. **What does it mean that Node.js is a JavaScript runtime?**  
   It means Node.js provides an environment where JavaScript can execute outside the browser, enabling server-side scripting and full-stack development with JavaScript.

4. **What is npm?**  
   npm (Node Package Manager) is a tool that manages JavaScript libraries and dependencies. It allows developers to install, update, and share packages.

5. **What version of Node.js are you running?**  
   _Run the following command in your terminal to find out:_  
   ```sh
   node -v
   ```
   _(Insert output here)_

6. **What version of npm are you running?**  
   _Run the following command in your terminal:_  
   ```sh
   npm -v
   ```
   _(Insert output here)_

7. **How to install a package (`jshint`) using npm?**  
   ```sh
   npm install -g jshint
   ```
   This installs `jshint` globally for use across multiple projects.

8. **What is Node.js used for?**  
   - Web servers  
   - RESTful APIs  
   - Real-time applications (chat, gaming)  
   - Command-line tools  
   - Microservices architecture

---

### **6 Reasons for Pair Programming**
1. **Greater efficiency** – Two developers catch errors faster and produce cleaner code.  
2. **Engaged collaboration** – Encourages active problem-solving and idea-sharing.  
3. **Learning from peers** – Gain new techniques and insights from different perspectives.  
4. **Social skills development** – Improves communication and teamwork.  
5. **Job interview readiness** – Mimics real-world technical interviews.  
6. **Work environment preparation** – Simulates workplace coding collaborations.

### **How Pair Programming Works**
- **Driver** – Writes the code.  
- **Navigator** – Reviews the code, suggests improvements.  
- They **switch roles frequently** to maintain engagement.

---

## **Things I Want to Know More About**
- How does Node.js handle asynchronous operations compared to Python or Ruby?  
- What are the best practices for managing dependencies in large Node.js projects?  
- How does Node.js compare to Deno, and when should I use one over the other?

---

Here’s how you can structure your **reading notes** based on this content.  

---

# **Express & Servers - Reading Notes**  
**Module:** Express & Servers  
**Date:** _(Insert Date)_

## **Why This Topic Matters**  
Understanding servers and Express.js is essential for full-stack web development. Servers handle requests, manage data, and communicate with front-end applications, making them a fundamental part of web applications.

---

## **Reading Questions and Answers**  

### **1. What is a server?**  
A server is a computer or software that provides services or resources to other devices (clients) over a network. In web development, a server processes client requests and responds with data, web pages, or APIs.

### **2. What is Express?**  
Express is a minimal and flexible **Node.js web application framework** that simplifies building servers and handling HTTP requests. It helps in routing, middleware integration, and API development.

### **3. What is CORS?**  
CORS (Cross-Origin Resource Sharing) is a security feature that controls how resources on a web server can be requested from different domains. It prevents unauthorized cross-origin requests but allows legitimate ones by defining permissions.

### **4. Why do we need a server?**  
- Servers handle **client requests** and return **responses** (e.g., sending web pages, serving APIs).  
- They store and **manage data** in databases.  
- They **authenticate users** and enforce security policies.  
- They allow **communication** between front-end applications and databases.

---

## **Basic Express Server**  

### **Code Breakdown**
```javascript
'use strict';

// Access .env file for environment variables
require('dotenv').config();

// Import Express framework
const express = require('express');

// Initialize Express app
const app = express();

// Import CORS to manage access permissions
const cors = require('cors');

// Allow all origins to access the server
app.use(cors());

// Get the port from the .env file
const PORT = process.env.PORT || 3001;

// Define a basic route
app.get('/', (request, response) => {
  response.send('Hello from the home route');
});

// Start the server
app.listen(PORT, () => console.log(`Listening on ${PORT}`));
```

### **Key Takeaways:**
- **`express()`** initializes the Express app.  
- **`app.use(cors())`** allows access to the server from any front-end application.  
- **`app.get('/', callback)`** defines a route that listens for GET requests.  
- **`app.listen(PORT, callback)`** starts the server on the specified port.

---

## **Handling API Requests**  

### **1. Setting Up a Route for Front-End Requests**
Front-end request using **Axios**:
```javascript
await axios.get('http://localhost:3001/cats');
```
Back-end route in **Express**:
```javascript
app.get('/cats', (request, response) => {
  response.send('Cats are the best');
});
```
💡 **Explanation:**  
- The front-end makes a GET request to `/cats`.  
- The server responds with `"Cats are the best"`.

### **2. Handling Queries from the Front-End**
Queries are **parameters** in a URL that help send data to the server.  

**Example Query URL:**  
```
http://localhost:3000/?city=seattle
```
Front-end request using **Axios**:
```javascript
await axios.get('http://localhost:3001/city', { params: { city: 'seattle' } });
```
Back-end code in **Express**:
```javascript
app.get('/city', (request, response) => {
  const city = request.query.city;
  response.send(`You sent the city of ${city}`);
});
```
💡 **Explanation:**  
- `request.query.city` extracts the `city` parameter from the query string.
- The response dynamically sends back `"You sent the city of Seattle"`.

---

## **Things I Want to Know More About**
- How does Express handle middleware for authentication?  
- What are best practices for structuring Express applications?  
- How does Express compare to Fastify or Koa for performance?

---

### **Citations**  
- _Express Documentation: [expressjs.com](https://expressjs.com)_  
- _MDN on CORS: [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)_  

---