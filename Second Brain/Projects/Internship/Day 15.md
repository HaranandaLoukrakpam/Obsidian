# [[Building an E-Commerce Product Listing Page using Fetch API]]

## Overview

This project demonstrates how to build a simple **E-Commerce Product Listing Page** using **HTML**, **CSS**, and **JavaScript**. Product information is fetched dynamically from the [[Fake Store API]] using the [[Fetch API]] and displayed as product cards.

---

# Project Structure

```
project/
│── index.html
│── index.css
└── index.js
```

---

# Technologies Used

- [[HTML]]
    
- [[CSS]]
    
- [[JavaScript]]
    
- [[Fetch API]]
    
- [[Async/Await]]
    
- [[DOM Manipulation]]
    
- [[CSS Grid]]
    
- [[Responsive Design]]
    

---

# Project Features

- Sticky navigation bar
    
- Search bar UI
    
- Product category tabs
    
- Product sorting UI
    
- Category filter UI
    
- Loading spinner while fetching data
    
- Dynamic product cards
    
- Responsive layout
    
- Modern IBM-inspired UI
    

---

# Fetching Data from an API

The products are fetched from the following endpoint:

```text
https://fakestoreapi.com/products
```

Using [[Fetch API]]:

```javascript
const res = await fetch("https://fakestoreapi.com/products");
const response = await res.json();
```

## Explanation

- `fetch()` sends an HTTP GET request.
    
- `await` waits until the request completes.
    
- `response.json()` converts JSON into a JavaScript object.
    
- The resulting array is passed to the rendering function.
    

---

# [[Async]] and [[Tags/Await]]

The project uses asynchronous programming.

```javascript
async function fetchData(){
    const res = await fetch(url);
    const data = await res.json();
}
```

## Benefits

- Cleaner syntax
    
- Easier to read
    
- Avoids callback nesting
    
- Waits for asynchronous operations to complete
    

---

# [[DOM Manipulation]]

Elements are created dynamically instead of writing HTML manually.

Methods used:

- `document.createElement()`
    
- `append()`
    
- `getElementById()`
    
- `innerText`
    
- `style`
    
- `src`
    

Example:

```javascript
const cardDiv = document.createElement("div");
const img = document.createElement("img");
const title = document.createElement("p");
```

---

# Rendering Products

Each product is displayed as a card.

Every card contains:

- Product Category
    
- Product Image
    
- Product Title
    
- Product Price
    
- Buy Now Button
    

Products are generated using:

```javascript
data.forEach((el)=>{
    // create card
});
```

---

# Product Card Flow

```
Fetch API
      │
      ▼
JSON Response
      │
      ▼
forEach()
      │
      ▼
Create HTML Elements
      │
      ▼
Append to Product Container
```

---

# [[Loading Spinner]]

A loading spinner is displayed until the API data has finished loading.

```javascript
loader.style.display = "none";
```

Purpose:

- Better User Experience
    
- Indicates data is loading
    

---

# HTML Layout

The page consists of:

## Header

Contains

- Logo
    
- Search Bar
    
- Navigation Menu
    

---

## Main Section

Contains

- Category Buttons
    
- Sorting Dropdown
    
- Category Filter Dropdown
    
- Loader
    
- Product Container
    

---

## Footer

Contains

- Company Links
    
- Support Links
    
- Quick Links
    

---

# CSS Concepts Used

## [[Flexbox]]

Used for

- Navigation Bar
    
- Footer
    
- Filters
    
- Tabs
    

Properties used

- `display:flex`
    
- `justify-content`
    
- `align-items`
    
- `gap`
    

---

## [[CSS Grid]]

Used for displaying products.

```css
display:grid;
grid-template-columns:repeat(4,1fr);
```

Benefits

- Equal columns
    
- Responsive layout
    
- Easy spacing
    

---

## [[Box Shadow]]

Used to create depth for product cards.

Example:

```css
box-shadow: ...
```

---

## [[Linear Gradient]]

Used for

- Buttons
    
- Logo
    
- Navigation
    
- Footer
    

Example

```css
background: linear-gradient(...);
```

---

## [[Sticky Header]]

```css
position:sticky;
top:0;
```

Keeps the navigation visible while scrolling.

---

## [[Media Queries]]

```css
@media(max-width:992px)
```

Used for responsive design.

Changes include

- Flexible navigation
    
- Wrapped menu
    
- Responsive footer
    

---

# JavaScript Methods Used

|Method|Purpose|
|---|---|
|`fetch()`|Request data from API|
|`json()`|Convert JSON response|
|`forEach()`|Iterate through products|
|`createElement()`|Create HTML elements|
|`append()`|Insert elements into DOM|
|`getElementById()`|Select HTML element|
|`innerText`|Add text|
|`style`|Apply inline CSS|

---

# API Response Structure

Each product contains

- `id`
    
- `title`
    
- `price`
    
- `description`
    
- `category`
    
- `image`
    
- `rating`
    

---

# Current Functionality

✅ Fetch product data

✅ Display products

✅ Dynamic product cards

✅ Loading animation

✅ Responsive layout

✅ Modern UI

---

# Planned Improvements

- [[Search Functionality]]
    
- [[Category Filtering]]
    
- [[Price Sorting]]
    
- [[Product Details Page]]
    
- [[Shopping Cart]]
    
- [[Wishlist]]
    
- [[Pagination]]
    
- [[Dark Mode]]
    

---

# Key Concepts Learned

- [[Asynchronous JavaScript]]
    
- [[Fetch API]]
    
- [[Promises]]
    
- [[JSON Parsing]]
    
- [[DOM Manipulation]]
    
- [[Dynamic Rendering]]
    
- [[Responsive Web Design]]
    
- [[CSS Grid]]
    
- [[Flexbox]]
    
- [[Media Queries]]
    
- [[Loading Spinner]]
    
- [[Event-Driven Programming]]
    

---

# Interview Questions

### What is the Fetch API?

A modern JavaScript API used to make HTTP requests asynchronously.

---

### Why use `async` and `await`?

They simplify asynchronous code and make it easier to read compared to Promise chaining.

---

### Why use `createElement()` instead of writing HTML?

It allows dynamic creation of content based on runtime data such as API responses.

---

### Why use CSS Grid?

It makes creating responsive, multi-column layouts simple and efficient.

---

### What is JSON?

JSON (JavaScript Object Notation) is a lightweight format used to exchange data between a client and server.

---

# Tags

#JavaScript #FetchAPI #AsyncAwait #DOM #CSSGrid #Flexbox #HTML #CSS #ResponsiveDesign #Frontend #WebDevelopment #API #Obsidian