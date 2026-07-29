# [[Fake Store API E-Commerce Project]]

## Overview
A simple e-commerce application built using:
- [[HTML]]
- [[CSS]]
- [[JavaScript]]
- [[Fetch API]]
- [[Local Storage]]
- [[Fake Store API]]

Features:
- Display all products
- View single product details
- Add products to cart
- Remove products from cart
- Store data using Local Storage

---

# [[Project Flow]]

```text
Fetch Products
      │
      ▼
Display Products
      │
 ┌────┴─────┐
 ▼          ▼
View      Add to Cart
Details        │
 │             ▼
 ▼       Local Storage (cart)
Single         │
Product        ▼
Page      Cart Page
                 │
                 ▼
           Remove Item
```

---

# [[Fetching Products]]

Products are fetched from:

```javascript
https://fakestoreapi.com/products
```

```javascript
async function fetchData(){
    const res = await fetch("https://fakestoreapi.com/products");
    const response = await res.json();
    renderData(response);
}
```

### Steps

1. Fetch data
2. Convert response into JSON
3. Pass data to `renderData()`

---

# [[renderData()]]

Responsible for displaying products dynamically.

```javascript
function renderData(data){
    data.forEach((el)=>{
        // Create elements
        // Append to DOM
    });
}
```

Each product card contains:

- Category
- Image
- Title
- Price
- Buy Now button
- View Details button
- Add to Cart button

---

# [[DOM Manipulation]]

Used methods:

```javascript
document.createElement()

append()

appendChild()

getElementById()

innerText

innerHTML

style.property
```

Example

```javascript
const img = document.createElement("img");
img.src = el.image;
```

---

# [[Loader]]

Loader is shown while products are loading.

```javascript
loader.style.display = "none";
```

Once API data arrives, the loader is hidden.

---

# [[View Details]]

Stores one product in Local Storage.

```javascript
localStorage.setItem(
    "singleProduct",
    JSON.stringify(product)
);
```

Redirects user

```javascript
window.location.href="singleProduct.html";
```

---

# [[Single Product Page]]

Reads stored product

```javascript
const singleProductData =
JSON.parse(localStorage.getItem("singleProduct"));
```

Displays

- Product Image
- Category
- Price
- Title
- Description
- Rating
- Rating Count

---

# [[Local Storage]]

Stores data permanently inside browser.

Convert object → string

```javascript
JSON.stringify(object)
```

Convert string → object

```javascript
JSON.parse(string)
```

Example

```javascript
localStorage.setItem(
    "cart",
    JSON.stringify(cart)
);

const cart =
JSON.parse(localStorage.getItem("cart"));
```

---

# [[Add to Cart]]

Retrieve cart

```javascript
const cart =
JSON.parse(localStorage.getItem("cart")) || [];
```

Add item

```javascript
cart.push(el);
```

Save

```javascript
localStorage.setItem(
    "cart",
    JSON.stringify(cart)
);
```

---

# [[Cart Page]]

Read cart

```javascript
const data =
JSON.parse(localStorage.getItem("cart"));
```

Display products using

```javascript
renderData(data);
```

---

# [[Remove Cart]]

Current implementation

```javascript
function removeCart(el,i){

    let cartData =
    JSON.parse(localStorage.getItem("cart")) || [];

    cartData.splice(i,1);

    localStorage.setItem(
        "cart",
        JSON.stringify(cartData)
    );

    renderData(cartData);
}
```

### Explanation

`splice(index, count)`

- Removes element
- Updates array
- Saves updated cart
- Re-renders page

---

# [[Array Methods Used]]

## [[forEach()]]

Loops through array

```javascript
data.forEach((el,i)=>{
});
```

---

## [[push()]]

Adds item

```javascript
cart.push(el);
```

---

## [[splice()]]

Removes item

```javascript
cartData.splice(i,1);
```

---

# [[Event Listeners]]

Buttons respond to clicks.

Example

```javascript
button.addEventListener("click",()=>{
    addToCart(el);
});
```

Another example

```javascript
button.addEventListener("click",()=>{
    removeCart(el,i);
});
```

---

# [[CSS Concepts]]

Used:

- CSS Grid
- Flexbox
- Responsive Layout
- Box Shadow
- Linear Gradient
- Sticky Navbar
- Media Queries
- Hover Effects
- Border Radius
- Animations
- Loader Spinner

Grid

```css
#productContainer{
    display:grid;
    grid-template-columns:repeat(4,1fr);
}
```

---

# [[Responsive Design]]

Uses media query

```css
@media(max-width:992px){
    ...
}
```

Adjusts

- Navbar
- Footer
- Layout

---

# [[Data Structure]]

Each product object

```javascript
{
    id,
    title,
    price,
    description,
    category,
    image,
    rating:{
        rate,
        count
    }
}
```

---

# [[Important JavaScript Concepts]]

- [[Async Await]]
- [[Fetch API]]
- [[Promises]]
- [[DOM Manipulation]]
- [[Events]]
- [[Functions]]
- [[Objects]]
- [[Arrays]]
- [[Local Storage]]
- [[JSON]]
- [[Template Literals]]

---

# [[Project Folder Structure]]

```text
Project
│
├── index.html
├── index.css
├── index.js
│
├── products.html
├── products.js
│
├── cart.html
├── cart.js
│
├── singleProduct.html
├── singleProduct.js
│
└── assets/
```

---

# [[Workflow Summary]]

```text
API
 │
 ▼
fetch()
 │
 ▼
JSON Data
 │
 ▼
renderData()
 │
 ▼
Display Products
 │
 ├───────────────┐
 ▼               ▼
Add Cart     View Details
 │               │
 ▼               ▼
Local Storage    Local Storage
 │               │
 ▼               ▼
Cart Page    Single Product Page
 │
 ▼
Remove Item
 │
 ▼
Update Local Storage
 │
 ▼
Render Again
```

---

# [[Key Learnings]]

- Fetch data from an API using `fetch()`
- Use `async/await` for asynchronous operations
- Dynamically create UI with DOM methods
- Store persistent data using Local Storage
- Convert objects with `JSON.stringify()` and `JSON.parse()`
- Navigate between pages while preserving state
- Build a basic e-commerce workflow without a backend
- Use CSS Grid, Flexbox, and media queries for responsive layouts
- Handle user interactions with event listeners
- Update the UI immediately after modifying application state