# JavaScript DOM Manipulation, Events & the `this` Keyword

## Tags

#javascript #web-development #frontend #dom #events #objects #functions

Related Notes:
- [[JavaScript]]
- [[DOM Manipulation]]
- [[Event Handling]]
- [[HTML Forms]]
- [[Objects]]
- [[Functions]]
- [[this Keyword]]
- [[Event Listeners]]

---

# Overview

This code demonstrates several fundamental JavaScript concepts:

- Selecting HTML elements
- Changing HTML content
- Applying CSS with JavaScript
- Creating elements dynamically
- Event handling
- Form submission
- Creating objects
- Object methods
- Using the `this` keyword

---

# Selecting Elements

HTML elements can be selected using their `id`.

Example:

```javascript
const para = document.getElementById("para");
```

This selects:

```html
<p id="para"></p>
```

Once selected, JavaScript can modify the element.

---

# Changing Text

```javascript
para.innerText = "I am paragraph text from JS file";
```

`innerText` changes the visible text of an element.

Before:

```
Paragraph
```

After:

```
I am paragraph text from JS file
```

---

# Styling Elements

JavaScript can apply CSS styles directly.

Example:

```javascript
para.style.border = "1px solid red";
para.style.backgroundColor = "teal";
para.style.color = "white";
```

Equivalent CSS:

```css
border: 1px solid red;
background-color: teal;
color: white;
```

---

# Creating Elements Dynamically

```javascript
const btn = document.createElement("button");
```

Creates:

```html
<button></button>
```

The button does not appear until it is added to the document.

---

# Setting Button Properties

```javascript
btn.innerText = "Click Me..!!";
```

Changes the button text.

Additional styling:

```javascript
btn.style.padding = "10px";
btn.style.border = "none";
btn.style.backgroundColor = "yellowgreen";
btn.style.color = "white";
btn.style.borderRadius = "5px";
```

---

# Adding Elements to the Page

```javascript
btnDiv.append(btn);
```

Adds the button inside the selected container.

Example:

```html
<div id="btn"></div>
```

After appending:

```html
<div id="btn">
    <button>Click Me..!!</button>
</div>
```

---

# Event Listeners

An event listener waits for a user action.

Example:

```javascript
btn.addEventListener("click", ()=>{
    console.log("clicked inside eventListener");
});
```

When the button is clicked:

```
clicked inside eventListener
```

is printed to the console.

---

# Common Events

| Event | Trigger |
|--------|---------|
| `click` | Mouse click |
| `submit` | Form submission |
| `input` | User types |
| `change` | Input value changes |
| `mouseover` | Mouse enters an element |
| `keydown` | Keyboard key pressed |

---

# Working with Forms

```javascript
let form = document.getElementById("form");
```

Selects the form.

---

# Handling Form Submission

```javascript
form.addEventListener("submit",(e)=>{
    e.preventDefault();
});
```

`preventDefault()` stops the page from refreshing after form submission.

This allows JavaScript to validate or process the form data.

---

# Reading Input Values

```javascript
let fullName = document.getElementById("fullName").value;
let email = document.getElementById("email").value;
let password = document.getElementById("password").value;
```

The `.value` property retrieves what the user entered.

---

# Creating an Object

```javascript
let obj = {
    fullName,
    email,
    password
};
```

Produces an object like:

```javascript
{
    fullName: "Alex",
    email: "alex@example.com",
    password: "123456"
}
```

---

# Printing an Object

```javascript
console.log(obj);
```

Displays the object in the browser console.

---

# JavaScript Objects

An object stores data as **key-value pairs**.

Example:

```javascript
let obj = {
    name: "Arpan",
    uni: "ADTU"
};
```

Properties:

- `name`
- `uni`

Values:

- `"Arpan"`
- `"ADTU"`

---

# Object Methods

Objects can also contain functions.

Example:

```javascript
let obj = {
    name: "Arpan",

    myFun: function(){
        console.log(this.name);
    }
}
```

Here, `myFun` is called an **object method**.

---

# The `this` Keyword

```javascript
console.log(this.name);
```

Inside an object method, `this` refers to the object that called the method.

Example:

```javascript
let obj = {
    name: "Arpan",

    myFun: function(){
        console.log(this.name);
    }
}
```

Calling:

```javascript
obj.myFun();
```

Output:

```
Arpan
```

`this.name` is equivalent to:

```javascript
obj.name
```

but is more flexible because it always refers to the current object.

---

# Calling Object Methods

```javascript
obj.myFun();
```

Execution Flow:

```
obj
 │
 ▼

myFun()

 │
 ▼

this

 │
 ▼

obj

 │
 ▼

obj.name

 │
 ▼

"Arpan"
```

Output:

```
Arpan
```

---

# Difference Between Property and Method

```javascript
let person = {
    name: "Alex",

    greet: function(){
        console.log("Hello");
    }
}
```

| Member | Type |
|---------|------|
| `name` | Property |
| `greet()` | Method |

---

# Key Functions Used

| Function | Purpose |
|----------|---------|
| `document.getElementById()` | Selects an HTML element |
| `createElement()` | Creates a new HTML element |
| `append()` | Adds an element to the DOM |
| `addEventListener()` | Attaches an event listener |
| `preventDefault()` | Stops the default browser action |
| `console.log()` | Prints output to the console |
| `innerText` | Changes visible text |
| `style` | Applies CSS using JavaScript |
| `.value` | Retrieves input field values |
| `this` | Refers to the current object |

---

# Execution Flow

```
Select HTML Element
        │
        ▼
Modify Content or Style
        │
        ▼
Create New Elements
        │
        ▼
Append to DOM
        │
        ▼
Wait for User Event
        │
        ▼
Execute Event Handler
        │
        ▼
Read User Input
        │
        ▼
Create Object
        │
        ▼
Call Object Method
        │
        ▼
Output Result
```

---

# Important Concepts

- `getElementById()` selects elements by ID.
- `innerText` changes visible text.
- `style` modifies CSS through JavaScript.
- `createElement()` creates new HTML elements.
- `append()` inserts elements into the DOM.
- `addEventListener()` responds to user interactions.
- `preventDefault()` prevents the browser's default form behavior.
- `.value` reads form input values.
- Objects store data using key-value pairs.
- Methods are functions stored inside objects.
- `this` refers to the object that invokes the method.

---

# Related Notes

- [[JavaScript]]
- [[DOM Manipulation]]
- [[HTML]]
- [[CSS]]
- [[Event Handling]]
- [[Event Listeners]]
- [[HTML Forms]]
- [[Objects]]
- [[Functions]]
- [[this Keyword]]
- [[Arrow Functions]]
- [[Browser Console]]