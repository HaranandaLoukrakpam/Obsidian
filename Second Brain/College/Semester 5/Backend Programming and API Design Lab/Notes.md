# [[Backend API]] — Revision Notes

**Subject:** Backend API Development  
**Technology:** [[Node.js]], [[Express.js]], [[SQLite]]  
**Practical:** Student REST API — CRUD Operations

---

# 1. [[HTTP]] — HyperText Transfer Protocol

## 1.1 [[HTTP]] Fundamentals

### What is [[HTTP]]?

HTTP stands for **HyperText Transfer Protocol**. It is a set of rules that allows a client (browser or application) and a server to communicate and exchange data over the web.

### What is the [[Client-Server Model]]?

It is a communication model in which:

1. The client sends a request to the server.
    
2. The server processes the request.
    
3. The server sends a response back to the client.
### What are [[HTTP Request and Response]]?

- **Request:** The message sent by the client asking the server to perform an action or provide data.
    
- **Response:** The message sent by the server containing the requested data or result, along with an HTTP status code.

Example: A client requests student details, and the server responds with the student's information.

---

## 1.2 [[HTTP Methods]]

### What are the main HTTP methods?

The five main HTTP methods are:

- `GET`
    
- `POST`
    
- `PUT`
    
- `PATCH`
    
- `DELETE`

### What is [[GET]] used for?

GET is used to retrieve or read data from the server. It does not modify server data.

Example:

```
GET /students
```

### What is [[POST]] used for?

POST is used to create new data on the server. The data is generally sent through the request body.

Example:

```
POST /students
```

### What is [[PUT]] used for?

PUT is used to completely replace or update an existing record.

Example:

```
PUT /students/1
```

### What is [[PATCH]] used for?

PATCH is used to update only specific fields of an existing record without replacing the entire record.

Example:

```
PATCH /students/1
```

### What is [[DELETE]] used for?

DELETE is used to remove an existing record from the server.

Example:

```
DELETE /students/1
```

### Difference Between [[PUT]] and [[PATCH]]

|PUT|PATCH|
|---|---|
|Updates the entire record.|Updates only selected fields.|
|Sends the complete updated data.|Sends only the modified data.|
|Replaces the existing representation.|Partially modifies the existing representation.|

### Which HTTP methods read data and which modify data?

|Method|Operation|
|---|---|
|GET|Read data|
|POST|Create data|
|PUT|Completely update data|
|PATCH|Partially update data|
|DELETE|Delete data|

**Remember:** GET is primarily used for reading data, while POST, PUT, PATCH and DELETE are used for modifying server resources.

---

## 1.3 [[HTTP Status Codes]]

### What is an HTTP Status Code?

An HTTP status code is a three-digit number returned by the server to indicate the result of a client's request.

### Main Categories of HTTP Status Codes

|Category|Meaning|
|---|---|
|1xx|Informational|
|2xx|Success|
|3xx|Redirection|
|4xx|Client Error|
|5xx|Server Error|

### Difference Between 200 and 201

|Status Code|Meaning|Explanation|
|---|---|---|
|200 OK|Successful request|The request was completed successfully.|
|201 Created|Resource created|A new resource was successfully created.|

### Difference Between 404 and 500

|Status Code|Meaning|Explanation|
|---|---|---|
|404 Not Found|Client Error|The requested resource does not exist.|
|500 Internal Server Error|Server Error|An unexpected problem occurred on the server.|

**Important HTTP Status Codes**

- `200` — OK
    
- `201` — Created
    
- `400` — Bad Request
    
- `401` — Unauthorized
    
- `403` — Forbidden
    
- `404` — Not Found
    
- `500` — Internal Server Error
    

---

## 1.4 [[URL]] — Uniform Resource Locator

### What is a URL?

URL stands for **Uniform Resource Locator**. It is the address used to locate a resource on the internet or a server.

Example:

```
http://localhost:3000/students/1
```

Parts of a URL:

- `http` — Protocol
    
- `localhost` — Hostname
    
- `3000` — Port number
    
- `/students/1` — Resource path
    

---

## 1.5 [[JSON]] — JavaScript Object Notation

### What is JSON?

JSON stands for **JavaScript Object Notation**. It is a lightweight text-based format used to store and exchange data between applications.

Example:

```
{
  "name": "Ravi",
  "course": "CS"
}
```

JSON is commonly used in REST APIs to exchange information between clients and servers.

---

# 2. [[API]] and [[REST API]]

## 2.1 [[API]] Fundamentals

### What is an API?

API stands for **Application Programming Interface**.

It is a set of rules and mechanisms that allows two different software applications to communicate and exchange information.

Example: A mobile application uses an API to retrieve student information from a server.

### What is a [[REST API]]?

REST stands for **Representational State Transfer**.

A REST API is an API architecture that uses URLs to identify resources and HTTP methods to perform operations on those resources.

Example:

```
GET /students
POST /students
PUT /students/1
DELETE /students/1
```

REST APIs commonly exchange data using JSON.

---

## 2.2 [[CRUD Operations]]

### What is CRUD?

CRUD stands for:

- **C — Create:** Add new data.
    
- **R — Read:** Retrieve existing data.
    
- **U — Update:** Modify existing data.
    
- **D — Delete:** Remove existing data.
    

### Mapping CRUD to HTTP Methods and SQL

|CRUD Operation|HTTP Method|SQL Command|
|---|---|---|
|Create|POST|INSERT|
|Read|GET|SELECT|
|Update|PUT / PATCH|UPDATE|
|Delete|DELETE|DELETE|

**Example:** In a student management system:

- Create — Add a new student.
    
- Read — Display student details.
    
- Update — Change a student's course.
    
- Delete — Remove a student record.
    

---

## 2.3 [[URL Parameters]] and [[Query Parameters]]

### How do we send values in a URL?

There are two common ways to send values through a URL.

**1. Path Parameters**

Path parameters are included directly in the URL path.

Example:

```
GET /students/5
```

In Express.js:

```
req.params.id
```

Here, `id` is the path parameter.

**2. Query Parameters**

Query parameters are added after a question mark (`?`) in the URL.

Example:

```
GET /students?course=CS
```

In Express.js:

```
req.query.course
```

Here, `course` is the query parameter.

### Difference Between Path Parameters and Query Parameters

| Path Parameters                       | Query Parameters                          |
| ------------------------------------- | ----------------------------------------- |
| Part of the URL path.                 | Added after `?` in the URL.               |
| Used to identify a specific resource. | Used for filtering, sorting or searching. |
| Accessed using `req.params`.          | Accessed using `req.query`.               |
| Example: `/students/5`                | Example: `/students?course=CS`            |

---

## 2.4 [[Request Body]]

### What is a Request Body?

A request body is the data sent by the client to the server along with an HTTP request.

It is commonly used with POST, PUT and PATCH methods.

Example:

```
{
  "name": "Ravi",
  "course": "CS"
}
```

In Express.js, the request body is accessed using:

```
req.body
```

---

# 3. [[Server]] Fundamentals

## 3.1 [[Server]]

### What is a Server?

A server is a program or computer that listens for client requests, processes them and sends appropriate responses.

### What are the different types of Servers?

|Server Type|Function|
|---|---|
|Web Server|Delivers web pages and static content.|
|Application Server|Runs application logic and backend code.|
|Database Server|Stores and manages database information.|
|File Server|Stores and provides access to files.|

## 3.2 [[Port Number]]

### What is a Port?

A port is a numerical identifier that helps a computer direct incoming network requests to the correct application or service.

Example:

```
http://localhost:3000
```

Here, `3000` is the port number.

**Port used in our practical:** `3000`

## 3.3 [[Localhost]]

### What is Localhost?

Localhost refers to the local computer on which a program or server is running.

Its standard IPv4 address is:

```
127.0.0.1
```

Example:

```
http://localhost:3000
```

It is commonly used to test applications locally before deployment.

---

# 4. [[Node.js]]

## 4.1 [[Node.js]] Fundamentals

### What is Node.js?

Node.js is a JavaScript runtime environment that allows JavaScript code to run outside a web browser.

It is mainly used to develop backend applications, web servers and APIs.

### Which JavaScript Engine does Node.js use?

Node.js uses Google's **V8 JavaScript Engine**, which is also used by the Google Chrome browser.

---

## 4.2 [[Non-Blocking I/O]]

### What is Non-Blocking I/O?

Non-blocking I/O allows Node.js to perform input/output operations without waiting for a slow operation to finish before moving to other tasks.

Example:

When Node.js reads a file or retrieves data from a database, it can continue handling other tasks while waiting for the operation to complete.

**Advantages:**

- Better performance for I/O-heavy applications.
    
- Efficient handling of multiple requests.
    
- Improved scalability.
    
- Less unnecessary waiting.
    

---

## 4.3 [[Single-Threaded Architecture]]

### Is Node.js Single-Threaded?

Yes, Node.js executes JavaScript using a single main thread called the event loop thread.

However, it can handle multiple concurrent requests through its non-blocking I/O architecture and asynchronous operations.

Some operations are also handled by the operating system or libuv's worker pool.

**Important:** Single-threaded does not mean Node.js can handle only one user at a time.

---

## 4.4 [[Node.js Modules]]

### What is a Module?

A module is a separate file or package containing reusable code that can be imported into another JavaScript file.

Example:

```
const express = require('express');
```

### What is require()?

`require()` is a CommonJS function used to import modules into a Node.js application.

Example:

```
const express = require('express');
const sqlite3 = require('sqlite3');
```

### What is module.exports?

`module.exports` is used to export functions, objects or variables from one module so that another file can import and use them.

Example:

```
// math.js
function add(a, b) {
    return a + b;
}

module.exports = add;
```

```
// app.js
const add = require('./math');

console.log(add(5, 3));
```

Output:

```
8
```

---

## 4.5 [[Node.js Project Files]]

### What is package.json?

`package.json` is the main configuration file of a Node.js project.

It contains:

- Project name.
    
- Project version.
    
- Project scripts.
    
- Dependencies.
    
- Development dependencies.
    
- Other project information.
    

### What is npm?

npm stands for **Node Package Manager**.

It is used to install, update, remove and manage packages or libraries in Node.js projects.

### What does npm install express do?

It installs the Express.js package into the project.

```
npm install express
```

It also:

- Creates or updates the `node_modules` folder.
    
- Adds Express to `package.json`.
    
- Updates `package-lock.json`.
    

**Other useful commands:**

```
npm install express -g
```

Installs a package globally.

```
npm install nodemon --save-dev
```

Installs nodemon as a development dependency.

### What is node_modules?

`node_modules` is the directory where npm stores all the packages and dependencies installed in a Node.js project.

It is generally not shared through GitHub. Other developers can recreate it using:

```
npm install
```

### What is package-lock.json?

`package-lock.json` records the exact versions of installed dependencies and their dependency information.

It helps ensure that the project uses a consistent package setup across different systems.

### What do npm init -y, npm start and npx do?

|Command|Function|
|---|---|
|`npm init -y`|Creates package.json with default settings.|
|`npm start`|Runs the start script defined in package.json.|
|`npx`|Executes a package command without requiring a permanent global installation.|

---

# 5. [[Express.js]]

## 5.1 [[Express.js]] Fundamentals

### What is Express.js?

Express.js is a minimal and flexible web application framework for Node.js.

It simplifies the development of web servers and REST APIs by providing features such as routing, middleware and request-response handling.

Example:

```
const express = require('express');

const app = express();

app.listen(3000);
```

---

## 5.2 [[Routing]]

### What is a Route?

A route is a combination of an HTTP method, URL path and handler function that determines how the server responds to a particular request.

Example:

```
app.get('/students', (req, res) => {
    res.send('List of students');
});
```

Here:

- `app.get()` — HTTP method.
    
- `/students` — URL path.
    
- `(req, res) => {}` — Handler function.
    

---

## 5.3 [[Middleware]]

### What is Middleware?

Middleware is a function that executes during the request-response cycle, after a request arrives and before the final response is sent.

It can:

- Execute code.
    
- Modify request and response objects.
    
- Process incoming data.
    
- End the request-response cycle.
    
- Pass control to the next middleware using `next()`.
    

Example:

```
app.use(express.json());
```

### What does express.json() do?

`express.json()` is built-in middleware in Express.js that parses incoming JSON request bodies and makes the parsed data available through `req.body`.

Example:

```
app.use(express.json());
```

Without this middleware, Express will not automatically parse incoming JSON request bodies.

---

## 5.4 [[Request and Response Objects]]

### What are req and res?

In Express.js:

**req — Request Object**

Contains information about the incoming client request.

Examples:

```
req.params
req.query
req.body
```

**res — Response Object**

Used to send a response back to the client.

Examples:

```
res.send()
res.json()
res.status()
```

### Difference Between res.send() and res.json()

|res.send()|res.json()|
|---|---|
|Sends text, HTML, buffers or other supported data.|Sends a JSON response.|
|Supports different response formats.|Serializes the supplied data as JSON.|
|Content type depends on the data or headers.|Sets the appropriate JSON content type.|

Example:

```
res.send('Hello World');
```

```
res.json({ name: 'Ravi' });
```

---

## 5.5 [[Server Listening]]

### What does app.listen(3000) do?

`app.listen(3000)` starts the Express server and makes it listen for incoming HTTP requests on port 3000.

Example:

```
app.listen(3000, () => {
    console.log('Server running on port 3000');
});
```

---

# 6. [[SQLite Database]]

## 6.1 [[SQLite]] Fundamentals

### What is SQLite?

SQLite is a lightweight, file-based relational database management system (RDBMS).

It stores the entire database in a single file, usually with the `.db` extension.

Example:

```
students.db
```

### Why is SQLite called Serverless?

SQLite is called serverless because it does not require a separate database server process to operate.

Instead, the application directly reads and writes data to the database file.

**Advantages:**

- Lightweight.
    
- Easy to configure.
    
- No separate database server required.
    
- Suitable for small applications and local development.
    

---

## 6.2 [[Database Structure]]

### What are Table, Row, Column and Primary Key?

|Term|Meaning|
|---|---|
|Table|Stores related data in a structured format.|
|Row|Represents one complete record.|
|Column|Represents a particular field or attribute.|
|Primary Key|Uniquely identifies each record in a table.|

Example:

**Students Table**

|id (Primary Key)|name|course|
|---|---|---|
|1|Ravi|CS|
|2|Aman|IT|
|3|Rahul|CSE|

Here:

- Table: Students
    
- Row: Individual student record.
    
- Columns: id, name, course.
    
- Primary Key: id.
    

---

## 6.3 [[SQLite Database Methods]]

### What do db.run(), db.get() and db.all() do?

These methods are commonly used with the Node.js `sqlite3` package to execute SQL queries.

|Method|Function|SQL Operation|
|---|---|---|
|`db.run()`|Executes a query without returning rows.|INSERT, UPDATE, DELETE|
|`db.get()`|Retrieves a single row.|SELECT one record|
|`db.all()`|Retrieves all matching rows.|SELECT multiple records|

**Examples:**

```
// Insert a record
db.run(
    'INSERT INTO students (name, course) VALUES (?, ?)',
    ['Ravi', 'CS']
);

// Retrieve one record
db.get(
    'SELECT * FROM students WHERE id = ?',
    [1],
    (err, row) => {
        console.log(row);
    }
);

// Retrieve all records
db.all(
    'SELECT * FROM students',
    [],
    (err, rows) => {
        console.log(rows);
    }
);
```

### What is the purpose of `?` in SQL queries?

The question mark (`?`) is a placeholder used in parameterized SQL queries.

It represents a value that is supplied separately when executing the query.

Example:

```
db.run(
    'INSERT INTO students (name, course) VALUES (?, ?)',
    ['Ravi', 'CS']
);
```

**Advantages:**

- Helps prevent SQL injection.
    
- Separates SQL commands from user input.
    
- Makes queries safer and more reliable.
    

---

# 7. [[REST API Practical]] — Student Management System

## 7.1 Practical Objective

**Task:** Build a REST API using Node.js, Express.js and SQLite to perform CRUD operations on student records.

The API will support:

1. Creating students.
    
2. Reading all students.
    
3. Reading a single student.
    
4. Updating student details.
    
5. Deleting student records.
    

### Technologies Used

|Technology|Purpose|
|---|---|
|Node.js|Runs JavaScript on the server.|
|Express.js|Creates the REST API and handles routes.|
|SQLite|Stores student records.|
|npm|Manages project dependencies.|
|cURL / Postman|Tests API endpoints.|

---

## 7.2 Step 1 — Project Setup

Create a project folder:

```
mkdir student-api
cd student-api
```

Initialize the Node.js project:

```
npm init -y
```

Install required packages:

```
npm install express sqlite3
```

### Project Structure

```
student-api/
│
├── node_modules/
├── package.json
├── package-lock.json
├── server.js
└── students.db
```

---

## 7.3 Step 2 — Create server.js

Create a file named `server.js` and write the following code.

### A. Import Modules and Initialize Express

```
const express = require('express');
const sqlite3 = require('sqlite3').verbose();

const app = express();
const PORT = 3000;

app.use(express.json());
```

**Explanation:**

- `express` imports the Express framework.
    
- `sqlite3` imports the SQLite database package.
    
- `app` creates an Express application.
    
- `PORT` defines the server port.
    
- `express.json()` parses incoming JSON request bodies.
    

### B. Connect to SQLite Database

```
const db = new sqlite3.Database('./students.db', (err) => {
    if (err) return console.error(err.message);

    console.log('Connected to SQLite database');
});
```

**Explanation:**

- Creates or connects to `students.db`.
    
- If the file does not exist, SQLite creates it.
    
- Displays an error if the connection fails.
    

### C. Create Students Table

```
db.run(`CREATE TABLE IF NOT EXISTS students (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    course TEXT NOT NULL
)`);
```

**Explanation:**

- `CREATE TABLE IF NOT EXISTS` creates the table only if it does not already exist.
    
- `id` uniquely identifies each student.
    
- `INTEGER` defines an integer field.
    
- `PRIMARY KEY` makes id the unique identifier.
    
- `AUTOINCREMENT` automatically generates IDs.
    
- `TEXT` stores text values.
    
- `NOT NULL` prevents empty SQL values in these columns.
    

---

## 7.4 Step 3 — Implement CRUD Operations

### A. CREATE — POST /students

Used to add a new student to the database.

```
app.post('/students', (req, res) => {
    const { name, course } = req.body;

    if (!name || !course) {
        return res.status(400).json({
            error: 'name and course are required'
        });
    }

    db.run(
        'INSERT INTO students (name, course) VALUES (?, ?)',
        [name, course],
        function (err) {
            if (err) {
                return res.status(500).json({
                    error: err.message
                });
            }

            res.status(201).json({
                id: this.lastID,
                name,
                course
            });
        }
    );
});
```

**Explanation:**

1. Receives student information through `req.body`.
    
2. Extracts name and course.
    
3. Checks whether both fields are provided.
    
4. Inserts the student into the database.
    
5. Returns the newly created student with status code `201`.
    

**Important:** `this.lastID` returns the ID of the last inserted row in the callback function.

### B. READ ALL — GET /students

Used to retrieve all student records.

```
app.get('/students', (req, res) => {
    db.all('SELECT * FROM students', [], (err, rows) => {
        if (err) {
            return res.status(500).json({
                error: err.message
            });
        }

        res.json(rows);
    });
});
```

**Explanation:**

1. Receives a GET request.
    
2. Executes `SELECT * FROM students`.
    
3. `db.all()` retrieves all matching records.
    
4. Returns the student records in JSON format.
    

### C. READ ONE — GET /students/

Used to retrieve a particular student using their ID.

```
app.get('/students/:id', (req, res) => {
    db.get(
        'SELECT * FROM students WHERE id = ?',
        [req.params.id],
        (err, row) => {
            if (err) {
                return res.status(500).json({
                    error: err.message
                });
            }

            if (!row) {
                return res.status(404).json({
                    error: 'Student not found'
                });
            }

            res.json(row);
        }
    );
});
```

**Explanation:**

1. Accepts the student ID through the URL.
    
2. `req.params.id` extracts the ID.
    
3. `db.get()` retrieves one matching record.
    
4. If no record exists, returns `404 Not Found`.
    
5. Otherwise, returns the student details.
    

### D. UPDATE — PUT /students/

Used to completely update an existing student's information.

```
app.put('/students/:id', (req, res) => {
    const { name, course } = req.body;

    db.run(
        'UPDATE students SET name = ?, course = ? WHERE id = ?',
        [name, course, req.params.id],
        function (err) {
            if (err) {
                return res.status(500).json({
                    error: err.message
                });
            }

            if (this.changes === 0) {
                return res.status(404).json({
                    error: 'Student not found'
                });
            }

            res.json({
                id: Number(req.params.id),
                name,
                course
            });
        }
    );
});
```

**Explanation:**

1. Receives the student ID through the URL.
    
2. Receives updated details through `req.body`.
    
3. Executes an SQL UPDATE query.
    
4. `this.changes` checks how many rows were modified.
    
5. If no record was updated, returns `404`.
    
6. Otherwise, returns the updated student information.
    

**Important:** `this.changes` returns the number of rows modified by the query.

### E. DELETE — DELETE /students/

Used to remove a student from the database.

```
app.delete('/students/:id', (req, res) => {
    db.run(
        'DELETE FROM students WHERE id = ?',
        [req.params.id],
        function (err) {
            if (err) {
                return res.status(500).json({
                    error: err.message
                });
            }

            if (this.changes === 0) {
                return res.status(404).json({
                    error: 'Student not found'
                });
            }

            res.json({
                message: 'Student deleted'
            });
        }
    );
});
```

**Explanation:**

1. Receives the student ID through the URL.
    
2. Executes the SQL DELETE query.
    
3. Checks whether a record was deleted.
    
4. Returns `404` if the student does not exist.
    
5. Otherwise, returns a success message.
    

---

## 7.5 Step 4 — Start the Server

Add the following code at the end of `server.js`:

```
app.listen(PORT, () => {
    console.log(`Server running at http://localhost:${PORT}`);
});
```

Run the application:

```
node server.js
```

Expected output:

```
Connected to SQLite database
Server running at http://localhost:3000
```

The API is now running locally.

---

## 7.6 Step 5 — Test API Using cURL

### 1. Create a Student — POST

```
curl -X POST http://localhost:3000/students \
-H "Content-Type: application/json" \
-d '{"name":"Ravi","course":"CS"}'
```

### 2. Read All Students — GET

```
curl http://localhost:3000/students
```

### 3. Read One Student — GET

```
curl http://localhost:3000/students/1
```

### 4. Update a Student — PUT

```
curl -X PUT http://localhost:3000/students/1 \
-H "Content-Type: application/json" \
-d '{"name":"Ravi Kumar","course":"IT"}'
```

### 5. Delete a Student — DELETE

```
curl -X DELETE http://localhost:3000/students/1
```

---

# 8. [[API Endpoint Summary]]

## 8.1 Student REST API Endpoints

|HTTP Method|Endpoint|Action|Success Code|
|---|---|---|---|
|POST|`/students`|Add a student|201|
|GET|`/students`|Get all students|200|
|GET|`/students/:id`|Get one student|200|
|PUT|`/students/:id`|Update a student|200|
|DELETE|`/students/:id`|Delete a student|200|

## 8.2 Complete CRUD Summary

|Operation|HTTP Method|Express Method|SQLite Method|SQL|
|---|---|---|---|---|
|Create|POST|`app.post()`|`db.run()`|INSERT|
|Read All|GET|`app.get()`|`db.all()`|SELECT|
|Read One|GET|`app.get()`|`db.get()`|SELECT|
|Update|PUT|`app.put()`|`db.run()`|UPDATE|
|Delete|DELETE|`app.delete()`|`db.run()`|DELETE|

---

# 9. [[Backend API]] — Quick Revision

## 9.1 Important Definitions

|Term|Quick Definition|
|---|---|
|HTTP|Protocol for communication between clients and servers.|
|API|Interface that allows software applications to communicate.|
|REST API|API architecture using resources and HTTP methods.|
|JSON|Lightweight data exchange format.|
|CRUD|Create, Read, Update and Delete.|
|Node.js|JavaScript runtime environment.|
|Express.js|Web framework for Node.js.|
|Middleware|Function that executes during the request-response cycle.|
|SQLite|Lightweight file-based relational database.|
|npm|Node Package Manager.|
|URL|Address of a resource.|
|Port|Number identifying an application or service endpoint.|
|Localhost|Refers to the local computer.|
|Primary Key|Uniquely identifies a database record.|
|Non-Blocking I/O|Allows other tasks to continue while I/O operations are pending.|

## 9.2 Important Express.js Properties

|Property / Method|Purpose|
|---|---|
|`req.params`|Access path parameters.|
|`req.query`|Access query parameters.|
|`req.body`|Access request body.|
|`res.send()`|Send a response.|
|`res.json()`|Send JSON response.|
|`res.status()`|Set HTTP status code.|
|`express.json()`|Parse JSON request bodies.|
|`app.listen()`|Start the server.|
|`app.get()`|Handle GET requests.|
|`app.post()`|Handle POST requests.|
|`app.put()`|Handle PUT requests.|
|`app.delete()`|Handle DELETE requests.|

## 9.3 Important SQLite Properties

|Method|Purpose|
|---|---|
|`db.run()`|Execute INSERT, UPDATE and DELETE queries.|
|`db.get()`|Retrieve one row.|
|`db.all()`|Retrieve multiple rows.|
|`this.lastID`|Get the ID of the last inserted record.|
|`this.changes`|Get the number of modified or deleted rows.|
|`?`|Placeholder for parameterized query values.|

---

# 10. [[Backend API]] — Important Practical Concepts

### Request-Response Flow

```
Client (Browser / Postman)
          |
          v
     HTTP Request
          |
          v
    Express Server
          |
          v
       Middleware
          |
          v
       API Route
          |
          v
     SQLite Database
          |
          v
      SQL Operation
          |
          v
     Express Response
          |
          v
        Client
```

### Important Points to Remember

1. Node.js runs JavaScript outside the browser.
    
2. Express.js simplifies backend server and API development.
    
3. HTTP methods define the action performed on a resource.
    
4. JSON is commonly used to exchange data between client and server.
    
5. Middleware processes requests before the route handler.
    
6. `req.body` contains incoming request data.
    
7. `req.params` extracts values from URL paths.
    
8. `req.query` extracts query string values.
    
9. SQLite stores data in a database file.
    
10. Parameterized SQL queries help prevent SQL injection.
    
11. `db.run()` executes database modification queries.
    
12. `db.get()` retrieves one record.
    
13. `db.all()` retrieves multiple records.
    

---

# [[Backend API]] #Revision #BackendDevelopment #NodeJS #ExpressJS #SQLite #RESTAPI #HTTP #CRUD #WebDevelopment