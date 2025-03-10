
**Psychological Safety in My Work Experience**

Psychological safety played a crucial role in my previous work experience, particularly during my time as a Navy Hospital Corpsman. In high-pressure environments, having the ability to speak up without fear of judgment or repercussions was essential for both patient safety and team efficiency. In situations where psychological safety was high, open communication led to better teamwork, improved morale, and more effective problem-solving. Conversely, in environments where team members felt hesitant to express concerns, errors were more likely to go unnoticed, and collaboration suffered.

**Moving Forward**

This article has reinforced the importance of fostering psychological safety in any team I work with. Moving forward, I will prioritize creating an environment where team members feel valued and heard. This includes actively listening to others, encouraging open discussions, providing constructive feedback, and acknowledging contributions. By fostering a culture of trust and respect, I can help build stronger, more effective teams.

----------

**REST and HTTP Protocol**

1.  **Who is Roy Fielding?** Roy Fielding is one of the principal authors of the HTTP specification and the creator of the REST (Representational State Transfer) architectural style. He helped define how web applications communicate over the internet.
    
2.  **Why don’t the techniques that we use in this class work well when we need to be able to talk to all of the machines in the world?** Many traditional techniques, such as using direct function calls or proprietary protocols, do not scale well for global communication. REST, built on standard HTTP methods, ensures that different systems can interact seamlessly regardless of their underlying technology.
    
3.  **What is the HTTP protocol that Fielding and his friends created?** HTTP (Hypertext Transfer Protocol) is a standard for communication between clients (browsers, applications) and servers. It defines how requests and responses are formatted and processed over the web.
    
4.  **What does a GET do?** A GET request retrieves data from a server. For example, `GET /users` would return a list of users from an API.
    
5.  **What does a POST do?** A POST request sends new data to a server to create a resource. For example, `POST /users` with user details would create a new user.
    
6.  **What does PUT do?** A PUT request updates an existing resource by replacing it entirely. For example, `PUT /users/1` with new user data would overwrite user 1’s information.
    
7.  **What does PATCH do?** A PATCH request updates specific parts of an existing resource instead of replacing it completely. For example, `PATCH /users/1` with an updated email would modify only the email field.
    

----------

**API Keys Status**

1.  **Geocoding API:** ✅ API key requested and received.
2.  **Weather Bit API:** ✅ API key requested and received.
3.  **Yelp API:** ✅ API key requested and received.
4.  **The Movie DB API:** ✅ API key requested and received.

All API keys have been securely stored and will be used for upcoming assignments and labs.

### **1. What is an API?**

An **API (Application Programming Interface)** is a set of rules that allows different software applications to communicate with each other. APIs define the methods and data structures that developers can use to interact with external systems, services, or databases.

In web development, APIs are commonly used to retrieve and send data between a client (e.g., a website or app) and a server.

Example:

-   **REST API**: Uses HTTP requests like GET, POST, PUT, DELETE.
-   **GraphQL API**: Allows fetching only the data you need using queries.

----------

### **2. What is Asynchronous Code? How does it relate to `async` and `await`?**

**Asynchronous code** allows JavaScript to perform time-consuming operations (like fetching data from an API) without freezing the rest of the program.

-   JavaScript is **single-threaded**, meaning it runs one operation at a time.
-   If an operation takes a long time (e.g., fetching data), it uses asynchronous code so other tasks can continue running.

#### `async` and `await`

-   `async`: Declares a function as asynchronous, meaning it can use `await`.
-   `await`: Pauses execution of the function until a promise resolves, preventing unnecessary nested `.then()` callbacks.

Example:

```javascript
async function fetchData() {
  const response = await fetch('https://pokeapi.co/api/v2/pokemon');
  const data = await response.json(); // Converts response to JSON
  console.log(data);
}

```

----------

### **3. Why Do You Need an API Key?**

An **API key** is a unique identifier used to authenticate a request to an API. It helps:

-   **Identify the user/application** making requests.
-   **Prevent abuse and overuse** by limiting the number of allowed requests.
-   **Grant access to specific features** of the API.

Some APIs are **public** (e.g., PokeAPI), while others (e.g., Google Maps API, OpenWeather API) require a key.

----------

### **4. What is an HTTP API Client?**

An **HTTP API client** is a tool that helps send and receive HTTP requests in JavaScript.

Examples:

-   **Fetch API** (built into JavaScript)
-   **Axios** (third-party library)
-   **Postman** (GUI-based API testing tool)

----------

### **5. What is Axios?**

**Axios** is a JavaScript library used for making HTTP requests. It simplifies working with APIs by handling:

-   Promises (`async/await` support)
-   Automatic JSON conversion
-   Request/response transformations
-   Error handling

Installation:

```bash
npm install axios

```

Example usage:

```javascript
import axios from 'axios';

async function getPokemon() {
  const response = await axios.get('https://pokeapi.co/api/v2/pokemon');
  console.log(response.data);
}

```

----------

### **6. Common Mistakes in `.env` Files**

Storing sensitive information like API keys or environment variables in a `.env` file is a good practice.

✅ Correct:

```
PORT=3000

```

❌ Common mistakes:

1.  **Spaces around `=`**
    
    ```
    PORT = 3000   // ❌ Incorrect
    
    ```
    
2.  **Adding a semicolon**
    
    ```
    PORT=3000;    // ❌ Incorrect
    
    ```
    
3.  **Using lowercase instead of UPPERCASE**
    
    ```
    port=3000     // ❌ Incorrect
    
    ```
    

To use an environment variable in JavaScript (Node.js):

```javascript
console.log(process.env.PORT);

```

----------

### **7. Making an API Call in React with Axios**

This React component fetches Pokémon data when a button is clicked:

```javascript
import React from 'react';
import axios from 'axios';

class App extends React.Component {
  getPokemon = async () => {
    const response = await axios.get('https://pokeapi.co/api/v2/pokemon');
    const pokemonArray = response.data;
  }

  render() {
    return (
      <button onClick={this.getPokemon}>Get Pokemon</button>
    );
  }
}

```

----------

### **8. Error Handling with `try/catch`**

Using a `try/catch` block prevents the app from crashing if an error occurs during the request.

Example:

```javascript
getPokemon = async () => {
  try {
    const response = await axios.get('https://pokeapi.co/api/v2/pokemon');
    const pokemonArray = response.data;
  } catch (err) {
    console.error("Error fetching Pokémon data:", err);
  }
};

```

-   If the API request fails (e.g., no internet connection), it logs an error instead of breaking the app.

----------

### **Final Thoughts**

-   **APIs** let applications communicate.
-   **Asynchronous code** prevents blocking the UI.
-   **Axios** simplifies API calls.
-   **`try/catch`** ensures robust error handling.

