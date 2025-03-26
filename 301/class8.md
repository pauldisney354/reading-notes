1. **What does REST stand for?**  
   - REST stands for **Representational State Transfer**.

2. **REST APIs are designed around a ____.**  
   - REST APIs are designed around **resources**.

3. **What is an identifier of a resource? Give an example.**  
   - A resource identifier is a unique way to reference a resource, usually a **URI (Uniform Resource Identifier)**.  
   - Example: `https://api.example.com/users/123`

4. **What are the most common HTTP verbs?**  
   - **GET** (Retrieve data)  
   - **POST** (Create a new resource)  
   - **PUT** (Update an existing resource)  
   - **PATCH** (Partially update a resource)  
   - **DELETE** (Remove a resource)

5. **What should the URIs be based on?**  
   - URIs should be based on **nouns that represent resources**, not actions.  
   - Example: `/users` instead of `/getUsers`

6. **Give an example of a good URI.**  
   - `https://api.example.com/products/456/reviews`

7. **What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?**  
   - A "chatty" API requires multiple requests to retrieve related data, increasing network load.  
   - This is **generally bad** because it affects performance and efficiency.

8. **What status code does a successful GET request return?**  
   - **200 OK**

9. **What status code does an unsuccessful GET request return?**  
   - Typically **404 Not Found** (if the resource doesn’t exist) or **400 Bad Request** (if the request is malformed).

10. **What status code does a successful POST request return?**  
    - **201 Created** (if a resource is successfully created)  
    - **200 OK** (if the request is processed but doesn’t create a new resource)

11. **What status code does a successful DELETE request return?**  
    - **204 No Content** (if deletion is successful with no response body)  
    - **200 OK** (if a response body is included)
    ---
1. **What is an API?**  
   - An **API (Application Programming Interface)** is a set of rules that allows different software applications to communicate with each other. It defines how requests and responses should be structured, enabling data exchange between clients and servers.

2. **Why do we need a server?**  
   - A **server** handles requests from clients, processes data, and sends responses. It is needed to:  
     - Store and manage data  
     - Handle authentication and security  
     - Process logic before sending data to the client  
     - Serve APIs for front-end applications

3. **What do we keep in our `.env` file?**  
   - The `.env` file stores **environment variables** such as:  
     - API keys  
     - Database credentials  
     - Port numbers  
     - Secret keys for authentication  
     - Any other sensitive or configurable information

4. **Nodemon will automatically detect changes that we make to all the files in our server, however, if we make a change to THIS file, we must restart nodemon for it to take effect.**  
   - **The `.env` file** is the file that requires a restart when modified because environment variables are only loaded when the server starts.

5. **True or False: all APIs require a key.**  
   - **False.** Not all APIs require a key. Some public APIs are open for use without authentication, while others require an API key for security and tracking.

6. **Axios API Call Explanation:**  
   - The provided axios call:  
     ```javascript
     const url = `http://urlToAPI/?key=${process.env.MY_API_KEY}&city=seattle`;
     const axiosResults = await axios.get(url);
     console.log(axiosResults.data);
     ```
   - Key takeaways:  
     - `await axios.get(url)` makes an asynchronous request.  
     - The function using this must be **async**.  
     - `axiosResults.data` contains the actual response data (not the full axios object).  