# LocalStorage Authentication (Register & Login)

## Tags

#javascript #web-development #frontend #authentication #localstorage #dom #forms

Related Notes:
- [[JavaScript]]
- [[DOM Manipulation]]
- [[HTML Forms]]
- [[Local Storage]]
- [[Authentication]]
- [[JSON]]
- [[Window Location]]
- [[Event Handling]]

---

# Overview

This project implements a **simple client-side authentication system** using **Local Storage**.

The application consists of three pages:

1. **Register Page** (`index.html`)
2. **Login Page** (`login.html`)
3. **Admin Page** (`admin.html`)

The user's registration details are stored in the browser using **Local Storage**. During login, the entered credentials are compared with the stored data. If they match, the user is redirected to the Admin page.

> **Note:** This method is suitable only for learning purposes. Real applications should authenticate users on a server and never store passwords in plain text.

---

# Project Structure

```
Project/

│── index.html        (Register Page)
│── login.html        (Login Page)
│── admin.html        (Admin Dashboard)
│── index.js          (Registration Logic)
│── login.js          (Login Logic)
```

---

# Register Page

The registration page collects:

- Full Name
- Email
- Password

```html
<form id="form">
```

The form sends data to JavaScript when submitted.

---

# Input Fields

```html
<input type="text" id="fullName">
<input type="email" id="email">
<input type="password" id="password">
```

Each input has a unique `id` so it can be accessed using JavaScript.

---

# Login Page

The login page asks for:

- Email
- Password

```html
<form id="form">
```

The user enters credentials that are compared with stored data.

---

# Admin Page

```html
<h1>Welcome to admin panel</h1>
```

This page is shown only after successful login.

---

# Event Listeners

Buttons respond to user actions using `addEventListener()`.

Example:

```javascript
registerButton.addEventListener("click", ()=>{
    window.location.href = "index.html";
});
```

When the Register button is clicked, the browser navigates to the registration page.

---

# Form Submission

```javascript
form.addEventListener("submit",(e)=>{
    e.preventDefault();
});
```

### `preventDefault()`

Normally, submitting a form reloads the page.

`preventDefault()` stops that behavior so JavaScript can validate the data first.

---

# Reading User Input

```javascript
let email = document.getElementById("email").value;
let password = document.getElementById("password").value;
```

The `.value` property retrieves the text entered into the input fields.

---

# Creating an Object

```javascript
let obj = {
    email,
    password
};
```

Creates an object containing the login credentials.

Example:

```javascript
{
    email: "alex@gmail.com",
    password: "123456"
}
```

---

# Local Storage

Local Storage stores data permanently in the browser.

Store data:

```javascript
localStorage.setItem("userData", JSON.stringify(arr));
```

Retrieve data:

```javascript
JSON.parse(localStorage.getItem("userData"));
```

Remove data:

```javascript
localStorage.removeItem("userData");
```

Clear all data:

```javascript
localStorage.clear();
```

---

# Why JSON.parse()?

Local Storage stores **only strings**.

Suppose the stored data is:

```javascript
"[{...},{...}]"
```

It must be converted back into a JavaScript array.

```javascript
let arr = JSON.parse(localStorage.getItem("userData")) || [];
```

If no data exists, an empty array is used.

---

# Login Validation

```javascript
for(let i = 0; i < arr.length; i++){
```

Loops through every registered user.

---

# Credential Verification

```javascript
if(
    arr[i].email == obj.email &&
    arr[i].password == obj.password
)
```

Checks whether both:

- Email matches
- Password matches

If both are correct, login succeeds.

---

# Redirecting Users

```javascript
window.location.href = "admin.html";
```

Redirects the browser to another page.

Other examples:

```javascript
window.location.href = "login.html";
window.location.href = "index.html";
```

---

# Showing Alerts

Successful login:

```javascript
alert("Welcome to admin page");
```

Failed login:

```javascript
alert("You are not authorized person or your credentials are incorrect");
```

Alerts provide feedback to the user.

---

# Login Flow

```
User enters Email & Password
            │
            ▼
Retrieve userData from Local Storage
            │
            ▼
Loop through registered users
            │
            ▼
Email and Password Match?
       │             │
      Yes            No
       │             │
       ▼             ▼
Redirect to      Show Error
admin.html         Alert
```

---

# Registration Flow

```
User enters details
        │
        ▼
Create User Object
        │
        ▼
Retrieve Existing Users
        │
        ▼
Push New User
        │
        ▼
Convert to JSON
        │
        ▼
Store in Local Storage
```

---

# Important JavaScript Concepts Used

## `addEventListener()`

Attaches an event to an HTML element.

```javascript
button.addEventListener("click", callback);
```

---

## `preventDefault()`

Stops the browser's default form submission.

```javascript
e.preventDefault();
```

---

## `document.getElementById()`

Selects an HTML element using its `id`.

```javascript
document.getElementById("email");
```

---

## `.value`

Reads the value entered into an input.

```javascript
email.value
```

---

## Objects

Stores related information together.

```javascript
let obj = {
    email,
    password
};
```

---

## Arrays

Stores multiple user objects.

```javascript
let arr = [];
```

---

## `for` Loop

Used to check every registered user.

```javascript
for(let i = 0; i < arr.length; i++)
```

---

## `JSON.stringify()`

Converts a JavaScript object or array into a string before storing it.

```javascript
JSON.stringify(arr);
```

---

## `JSON.parse()`

Converts the stored string back into a JavaScript object.

```javascript
JSON.parse(data);
```

---

## `window.location.href`

Navigates to another webpage.

```javascript
window.location.href = "admin.html";
```

---

# Limitations of This Project

This authentication system is **not secure** because:

- Passwords are stored in plain text.
- Anyone can inspect Local Storage in the browser.
- Authentication is performed entirely on the client side.
- There is no server-side validation.
- There is no session management.
- There is no password hashing or encryption.

This approach is useful only for practicing JavaScript concepts.

---

# Improvements

Possible enhancements include:

- Validate empty input fields.
- Prevent duplicate email registrations.
- Hash passwords before storage.
- Add Logout functionality.
- Store logged-in user information.
- Protect the Admin page from unauthorized access.
- Replace Local Storage with a backend database.
- Use authentication methods such as [[JWT]] or sessions.

---

# Key Concepts Learned

- Creating HTML forms
- Handling form submission
- Event listeners
- Reading input values
- JavaScript objects
- Arrays
- Local Storage
- `JSON.stringify()`
- `JSON.parse()`
- Authentication logic
- Login validation
- Redirecting between pages
- DOM Manipulation

---

# Related Notes

- [[JavaScript]]
- [[DOM Manipulation]]
- [[HTML Forms]]
- [[Event Handling]]
- [[Local Storage]]
- [[Authentication]]
- [[JSON]]
- [[Window Object]]
- [[Browser Storage]]
- [[Arrays]]
- [[Objects]]
- [[Functions]]
- [[Control Flow]]
- [[Conditional Statements]]
- [[Loops]]