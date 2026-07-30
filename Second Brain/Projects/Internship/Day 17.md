# [[Express.js]] Backend with [[Fetch API]]

## Overview

This project demonstrates how to:

- Create a simple backend using [[Express.js]]
    
- Enable cross-origin requests using [[CORS]]
    
- Store data in an array
    
- Create API endpoints
    
- Consume the API from the frontend using the [[Fetch API]]
    
- Display the fetched data dynamically using [[JavaScript DOM]]
    

---

# Project Structure

```text
project/
│
├── backend/
│   ├── index.js
│   ├── package.json
│   └── .env
│
└── frontend/
    ├── index.html
    └── index.js
```

---

# [[Package.json]]

The `package.json` file contains project information and dependencies.

### Important Dependencies

### [[Express.js]]

Used to create the web server.

```bash
npm install express
```

### [[CORS]]

Allows the frontend to access the backend running on another port.

```bash
npm install cors
```

### [[dotenv]]

Loads environment variables from a `.env` file.

```bash
npm install dotenv
```

### [[Nodemon]]

Automatically restarts the server whenever files change.

```bash
npm install nodemon
```

---

# Server Setup

```javascript
const express = require("express");
const cors = require("cors");
require("dotenv").config();

const app = express();

app.use(cors());
```

### Explanation

- `express()` creates the server.
    
- `cors()` enables communication between frontend and backend.
    
- `dotenv` loads variables such as the server port.
    

---

# Environment Variables

Create a `.env` file.

```text
PORT=8000
```

Access it using:

```javascript
process.env.PORT
```

This keeps configuration separate from source code.

---

# Root Route

```javascript
app.get("/", (req, res)=>{
    res.send("<h2>Welcome to FS Server</h2>");
});
```

Visiting

```
http://localhost:8000/
```

returns

```html
<h2>Welcome to FS Server</h2>
```

---

# Sample Data

```javascript
const users = [
    {
        name:"Mahavir",
        uni:"ADTU"
    },
    {
        name:"Ruth",
        uni:"ADTU"
    },
    {
        name:"Anreev",
        uni:"ADTU"
    },
    {
        name:"Aman",
        uni:"ADTU"
    }
]
```

This array acts as a temporary database.

---

# API Route

```javascript
app.get("/users",(req,res)=>{
    res.send(users);
})
```

Request:

```
GET /users
```

Response:

```json
[
  {
    "name":"Mahavir",
    "uni":"ADTU"
  },
  {
    "name":"Ruth",
    "uni":"ADTU"
  }
]
```

Express automatically converts JavaScript objects into JSON.

---

# Starting the Server

```javascript
const PORT = process.env.PORT;

app.listen(PORT, ()=>{
    console.log("Server is running on port",PORT);
})
```

Run:

```bash
npm run server
```

Output

```
Server is running on port 8000
```

---

# Frontend HTML

```html
<body>

<h3>Hello there..!!</h3>

<div id="container"></div>

<script src="index.js"></script>

</body>
```

The `container` div is where the fetched user data will be displayed.

---

# [[Fetch API]]

```javascript
const fetchData = async()=>{
    const res = await fetch("http://localhost:8000/users");

    const response = await res.json();

    renderData(response);
}
```

### Step-by-Step

### Step 1

```javascript
fetch(...)
```

Sends a GET request.

---

### Step 2

```javascript
await
```

Waits until the request is completed.

---

### Step 3

```javascript
res.json()
```

Converts JSON into a JavaScript object.

---

### Step 4

```javascript
renderData(response)
```

Passes the received array to another function for rendering.

---

# Rendering Data

```javascript
function renderData(data){

    const parent = document.getElementById("container");

    data.forEach((el)=>{

        const childDiv = document.createElement("div");

        childDiv.style.border="1px solid green";

        const name=document.createElement("p");
        name.innerText=`Name:- ${el.name}`;

        const uni=document.createElement("p");
        uni.innerText=`University:- ${el.uni}`;

        childDiv.append(name,uni);

        parent.append(childDiv);

    });

}
```

### Workflow

```
Array

↓

forEach()

↓

Create <div>

↓

Create <p> for name

↓

Create <p> for university

↓

Append paragraphs to div

↓

Append div to container
```

---

# Function Call

```javascript
fetchData();
```

Execution flow:

```
Page Loads

↓

fetchData()

↓

GET Request

↓

Receive JSON

↓

renderData()

↓

Display Cards on Screen
```

---

# Response Flow

```
Browser

↓

Fetch API

↓

Express Server

↓

/users Route

↓

users Array

↓

JSON Response

↓

Frontend

↓

DOM Rendering
```

---

# Important Concepts

## [[Express.js]]

- Lightweight backend framework
    
- Handles routing
    
- Sends responses
    
- Builds REST APIs
    

---

## [[Routes]]

```javascript
app.get("/users", callback)
```

- `/` → Home route
    
- `/users` → Returns user data
    

---

## [[CORS]]

Without CORS:

```
Frontend ❌ Backend
```

With

```javascript
app.use(cors());
```

```
Frontend ✅ Backend
```

---

## [[Environment Variables]]

Used for:

- Port numbers
    
- Database URLs
    
- API keys
    
- Secret values
    

Example

```javascript
process.env.PORT
```

---

## [[JSON]]

JSON is the standard format used for exchanging data between frontend and backend.

Example:

```json
{
  "name":"Mahavir",
  "uni":"ADTU"
}
```

---

## [[Async Await]]

```javascript
const res = await fetch(...)
```

`await` pauses execution until the promise is resolved, making asynchronous code easier to read.

---

## [[DOM Manipulation]]

Methods used:

```javascript
document.createElement()

append()

getElementById()

innerText
```

These methods create and insert HTML elements dynamically.

---

# Complete Request Lifecycle

```
Frontend loads

↓

fetchData()

↓

fetch()

↓

GET /users

↓

Express Route

↓

Users Array

↓

JSON Response

↓

res.json()

↓

renderData()

↓

DOM Updates

↓

Users Visible on Webpage
```

---

# Key Takeaways

- [[Express.js]] creates the backend server.
    
- [[CORS]] allows communication between different origins.
    
- [[dotenv]] stores configuration such as the server port.
    
- [[Routes]] define API endpoints.
    
- [[JSON]] is used to exchange data.
    
- [[Fetch API]] retrieves data from the server.
    
- [[Async Await]] simplifies asynchronous operations.
    
- [[DOM Manipulation]] displays the fetched data dynamically.
    
- [[Nodemon]] automatically restarts the server during development.