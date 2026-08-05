# Asynchronous JavaScript, Fetch API & DOM Manipulation

## Tags

[[JavaScript]] [[Web Development]] [[Frontend]] [[Asynchronous Programming]] [[DOM]] [[API]] [[Promises]]

Related Notes:
- [[JavaScript]]
- [[Asynchronous JavaScript]]
- [[Synchronous JavaScript]]
- [[Event Loop]]
- [[Call Stack]]
- [[Web APIs]]
- [[Promises]]
- [[Async Await]]
- [[Fetch API]]
- [[DOM Manipulation]]
- [[JSON]]
- [[HTTP Requests]]
- [[API]]
- [[ES6]]

---

# Overview

JavaScript is a **single-threaded** programming language. It executes **one line of code at a time** using a single call stack.

Although JavaScript is single-threaded, it can perform asynchronous operations through browser-provided **Web APIs**, allowing long-running tasks to execute without blocking the main thread.

---

# Synchronous JavaScript

Synchronous code executes **line by line** in the exact order it is written.

Example:

```javascript
console.log("First");
console.log("Second");
console.log("Third");
```

Output:

```
First
Second
Third
```

Characteristics:

- Executes sequentially.
- Blocks the next statement until the current one finishes.
- Easy to understand.
- Not suitable for time-consuming operations.

---

# Asynchronous JavaScript

Asynchronous code allows JavaScript to continue executing while waiting for tasks such as:

- API requests
- Timers
- File operations
- Database requests
- User interactions

Examples:

- `setTimeout()`
- `fetch()`
- `Promise`
- `async/await`

---

# Example: setTimeout()

```javascript
console.log("Before");

setTimeout(() => {
    console.log("Inside Timeout");
}, 2000);

console.log("After");
```

Output:

```
Before
After
Inside Timeout
```

Even though `setTimeout()` appears in the middle, JavaScript continues executing because the timer runs asynchronously.

---

# setTimeout with Different Delays

```javascript
setTimeout(()=>{ console.log("Task 1") },2000);
setTimeout(()=>{ console.log("Task 2") },1000);
setTimeout(()=>{ console.log("Task 3") },3000);
setTimeout(()=>{ console.log("Task 4") },0);
```

Execution Order:

```
Task 4
Task 2
Task 1
Task 3
```

### Why?

Even with `0ms`, `setTimeout` is **not executed immediately**.

The callback is placed in the **Callback Queue** and waits until:

1. Call Stack becomes empty.
2. Event Loop moves it back to the Call Stack.

See:
- [[Event Loop]]
- [[Call Stack]]
- [[Callback Queue]]

---

# Promises

A **Promise** represents the eventual completion or failure of an asynchronous operation.

Three possible states:

```
Pending
   │
   ├──► Fulfilled
   │
   └──► Rejected
```

### Pending

Operation is still running.

### Fulfilled

Operation completed successfully.

### Rejected

Operation failed.

---

# Async Functions

Declaring an async function:

```javascript
async function myFun(){
    console.log("Async execution");
}
```

An `async` function always returns a **Promise**.

---

# await Keyword

`await` pauses execution inside an async function until a Promise resolves.

Example:

```javascript
const response = await fetch(url);
```

Advantages:

- Cleaner syntax
- Easier to read
- Avoids callback nesting
- Makes asynchronous code look synchronous

---

# Fetch API

The **Fetch API** is used to make HTTP requests.

Example:

```javascript
fetch(url)
```

Returns:

```
Promise<Response>
```

The response must usually be converted to JSON.

Example:

```javascript
const res = await fetch(url);
const data = await res.json();
```

---

# Understanding getData()

```javascript
async function getData(){

    const res = await fetch("https://fakestoreapi.com/products");

    const response = await res.json();

    appendData(response);
}
```

### Step 1

Request data from the Fake Store API.

```
fetch()
```

↓

Returns a Promise.

---

### Step 2

Wait until the response arrives.

```javascript
await fetch(...)
```

---

### Step 3

Convert the response into a JavaScript object.

```javascript
await res.json();
```

---

### Step 4

Pass the data to another function.

```javascript
appendData(response);
```

---

# DOM Manipulation

The function

```javascript
appendData(data)
```

creates HTML elements dynamically.

It performs the following tasks:

- Selects the parent element.
- Loops through products.
- Creates a product card.
- Inserts product information.
- Displays everything on the webpage.

---

# Selecting an Element

```javascript
const parentDiv = document.getElementById("parent");
```

Finds the element whose id is `"parent"`.

---

# Looping Through Data

```javascript
data.forEach((el)=>{
```

Each product is processed individually.

`el` represents one product object.

Example:

```javascript
{
    title,
    price,
    image,
    category,
    description
}
```

---

# Creating Elements

```javascript
const childDiv = document.createElement("div");
```

Creates:

```html
<div></div>
```

Similarly,

```javascript
document.createElement("img")
document.createElement("p")
document.createElement("button")
```

creates new HTML elements.

---

# Styling with JavaScript

Example:

```javascript
childDiv.style.textAlign = "center";
```

Styles are applied directly through the `style` property.

Examples from the code:

- `textAlign`
- `boxShadow`
- `width`
- `height`
- `backgroundColor`
- `padding`
- `color`

---

# Displaying Data

Example:

```javascript
cat.innerText = el.category;
```

Displays:

```
Men's Clothing
```

Similarly,

```javascript
title.innerText = el.title;
price.innerText = el.price;
desc.innerText = el.description;
```

---

# Displaying Images

```javascript
img.src = el.image;
```

Sets the image source.

```javascript
img.style.width = "200px";
img.style.height = "200px";
```

Controls image size.

---

# Creating a Button

```javascript
const button = document.createElement("button");

button.innerText = "Buy Now";
```

Adds a clickable button for each product.

---

# Appending Elements

```javascript
childDiv.append(
    cat,
    img,
    title,
    price,
    desc,
    button
);
```

Places all elements inside the product card.

Then:

```javascript
parentDiv.append(childDiv);
```

Adds the product card to the webpage.

---

# Overall Execution Flow

```
getData()

      │
      ▼

fetch(API)

      │
      ▼

Promise

      │
      ▼

await

      │
      ▼

JSON Data

      │
      ▼

appendData()

      │
      ▼

Loop through products

      │
      ▼

Create HTML Elements

      │
      ▼

Insert Data

      │
      ▼

Display Products on Webpage
```

---

# Key Functions Used

| Function | Purpose |
|----------|---------|
| `fetch()` | Makes an HTTP request |
| `await` | Waits for a Promise |
| `async` | Declares an asynchronous function |
| `res.json()` | Converts JSON response to JavaScript object |
| `document.getElementById()` | Selects an HTML element |
| `document.createElement()` | Creates a new HTML element |
| `append()` | Adds child elements |
| `forEach()` | Iterates through an array |
| `innerText` | Sets text content |
| `style` | Applies CSS styles |
| `img.src` | Sets image URL |

---

# Important Concepts

- JavaScript is **single-threaded**.
- Synchronous code executes one statement at a time.
- Asynchronous operations prevent blocking.
- `setTimeout()` schedules future execution.
- Promises represent asynchronous results.
- `async/await` simplifies Promise handling.
- `fetch()` retrieves data from APIs.
- `res.json()` converts JSON into JavaScript objects.
- DOM Manipulation allows HTML to be created dynamically.
- `append()` inserts elements into the webpage.
- `forEach()` is commonly used to render lists of data.

---

# Related Notes

- [[JavaScript]]
- [[Synchronous JavaScript]]
- [[Asynchronous JavaScript]]
- [[Event Loop]]
- [[Call Stack]]
- [[Callback Queue]]
- [[Web APIs]]
- [[Promises]]
- [[Async Await]]
- [[Fetch API]]
- [[DOM Manipulation]]
- [[JSON]]
- [[REST API]]
- [[HTTP Requests]]
- [[Arrays]]
- [[Functions]]
- [[ES6]]