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
