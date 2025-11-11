# Express.js

### What is Express.js?
- A **backend web framework for Node.js** used to build servers and APIs
- Handles **routing** (deciding what happens when a user visits a URL)
- Provides tools for **middleware** (functions that run before a request is completed)
- Makes it easy to build **REST APIs**, handle requests, send responses, and manage data
- Lightweight and flexible — you add only the features you need
- Commonly used in **MERN stack** apps (MongoDB, Express, React, Node)

# Setup

``` bash
npm init -y
npm install express
```
#### Create a simple server

``` js
const express = require("express"); // Imports the Express framework to file
const app = express(); // creates an Express application instance
// app is not the main object for defining routes, middleware, and server behavior

app.get("/", (req, res) => {
    res.send("Hello World");
});
```

- `app.get("/")` defines a **route handler** for HTTP GET requests to the root URL (`/`).
- This means: when a user visits `http://localhost:3000/`, run this function.
- The callback function receives:
    - **`req`** → the incoming request object (data the client sends)
    - **`res`** → the response object (what you send back)
- `res.send("Hello World")` sends a plain text response back to the browser.
- 

``` js
app.listen(3000, () => console.log("Server running on port 3000"));
```
- Starts the server and makes it listen for incoming requests on **port 3000**.
- The callback function runs only once when the server successfully starts.
- `console.log(...)` is just a message to confirm your server is running.
  
#### What this server actually does
- Launches a local web server using Express
- Listens on port 3000
- Responds with **“Hello World”** whenever someone visits `/`

---

# Routing in Express.js

Routing defines how your server responds to different HTTP requests. Each route matches a specific URL path and HTTP method, then runs a handler function to generate a response.

#### HTTP Methods & Their Purpose

These methods represent different types of actions a client can request:
- **`GET`** – Retrieve data or a page (read-only, idempotent)
- **`POST`** – Create a new resource or trigger an action (non-idempotent)
- **`PUT`** – Fully replace an existing resource (idempotent)
- **`PATCH`** – Partially update an existing resource
- **`DELETE`** – Remove a resource
- **`ALL`** – Match any HTTP method on a given path
    `app.all('/path', handler);`

#### Example: Separate GET and POST Routes
``` js
app.get('/hello', (req, res) => {
    res.send('GET request');
});

app.post('/hello', (req, res) => {
    res.send('POST request');
});
```

#### Request & Response Objects

Every route handler receives two important objects:
- **`req`** – incoming request (data sent _from_ the client)
- **`res`** – outgoing response (data sent _to_ the client)
    
#### Request Object (`req`)

The `req` object contains all information about the incoming request.
#### 1. `req.params` — Route parameters

Used for dynamic segments in the URL.
``` js
app.get('/user/:id', (req, res) => {
    console.log(req.params.id); // e.g., 42
	res.send('User route'); 
});
```

#### 2. `req.query` — Query string data

For URLs like: `/search?q=react&page=2`
``` js
app.get('/search', (req, res) => { 
    console.log(req.query.q);   // "react" 
    console.log(req.query.page) // "2"
    res.send('Search route'); 
});
```

#### 3. `req.body` — Request body data

Available when using body-parsing middleware:
``` js
app.use(express.json()); // enables JSON body parsing
```
Example:

`app.post('/login', (req, res) => {     console.log(req.body.email);     res.send('Login route'); });`

#### Response Object (`res`)

The `res` object is used to send data back to the client.

#### 1. `res.send()`

Sends text, buffers, or objects.
``` js
res.send("Hello World");
```

#### 2. `res.json()`

Sends JSON formatted data.
``` js
res.json({ status: "ok", items: [1, 2, 3] });
```

#### 3. `res.status()`

Sets HTTP status code.
```
res.status(404).send("Not found");
```

#### 4. Combine `status()` + `json()`

``` js
res.status(200).json({ message: "Success" });
```

#### 5. `res.redirect()`

Redirects the client to another URL.
``` js
res.redirect('/login');
```

# **Putting It All Together**

Here’s a complete example showing parameters, queries, body, and responses:

`app.use(express.json());  app.get('/items/:id', (req, res) => {     console.log(req.params.id);     console.log(req.query.sort);     res.json({ message: "Item fetched" }); });  app.post('/items', (req, res) => {     console.log(req.body);     res.status(201).json({ message: "Item created" }); });`

---

If you'd like, I can rewrite the next section of your study guide too (middleware, routing grouping, request lifecycle, etc.).
---

# Middleware

#### What is middleware?
- Functions that run **before** route handlers.
- Used for parsing JSON, authentication, logging, etc.
- Runs **in order** of declaration.
#### Creating Middleware
``` js
function logger(req, res, next) {
    console.log(`${req.method} ${req.url}`);
    next(); 
}

app.use(logger);
```

#### Built-in Middleware
``` js
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
```

---

# Static Files

#### Serving static assets
``` js
app.use(express.static("public"));
```

# Route Parameters

#### Dynamic routes
``` js
app.get("/post/:postId", (req, res) => {
     res.send(`Post ID: ${req.params.postId}`);
});
```
# Query Parameters

``` js
app.get("/search", (req, res) => {
	res.send(req.query); 
});
```
# JSON APIs

#### Sending JSON

``` js
app.get("/api/data", (req, res) => {
	res.json({ name: "Elven", role: "Developer" });
});
```

# Error Handling

#### Error middleware (must have 4 params)

``` js
app.use((err, req, res, next) => {     
	console.error(err);     
	res.status(500).send("Something broke!");
});
```

# Routers

#### Create a router module
``` js
// userRoutes.js const express = require("express"); 
const router = express.Router();
router.get("/", (req, res) => res.send("All users"));
router.get("/:id", (req, res) => res.send(`User ${req.params.id}`));
module.exports = router;

// server.js const userRoutes = require("./userRoutes");
app.use("/users", userRoutes);
```

# Environment Variables

#### dotenv
``` js
npm install dotenv

require("dotenv").config(); const PORT = process.env.PORT || 3000;
```


# Listening on a Port

``` js
app.listen(PORT, () => console.log(`Running on port ${PORT}`));
```