# Day 8 – JavaScript Basics: Variables, Data Types, Operators, Arrays, and Conditional Statements

## Overview

This lesson introduces the fundamentals of **JavaScript**, including variables, data types, comparison operators, conditional statements, arrays, and common array methods. It also demonstrates how JavaScript is linked to an HTML document using an external `.js` file.

---

# Concepts Covered

## 1. Linking JavaScript

JavaScript is linked using the `<script>` tag.

```html
<script src="index.js"></script>
```

### Purpose

- Loads an external JavaScript file.
- Keeps HTML and JavaScript separate.
- Makes code easier to maintain.

---

## 2. Variables

Variables are used to store data.

### `let`

```javascript
let firstName = "John";
```

- Can be reassigned.
- Block scoped.
- Preferred for variables whose values may change.

---

### `const`

```javascript
const PI = 3.14159;
```

- Cannot be reassigned.
- Block scoped.
- Used for constant values.

---

### `var`

```javascript
var age = 20;
```

- Function scoped.
- Older way of declaring variables.
- Generally avoided in modern JavaScript.

---

## 3. Concatenation

Joins strings together.

```javascript
console.log(firstName + " " + lastName);
```

Output

```
John Doe
```

---

## 4. Data Types

JavaScript supports several data types.

### String

```javascript
let name = "John";
```

---

### Number

```javascript
let age = 20;
let decimal = 5.6;
```

---

### Boolean

```javascript
let isStudent = true;
```

---

### Null

```javascript
let value = null;
```

Represents an intentional empty value.

---

### Undefined

```javascript
let value;
```

Variable declared but not assigned.

---

### Array

```javascript
let arr = [1,2,3];
```

Stores multiple values.

---

### Object

```javascript
let person = {
    name:"Alex",
    age:21
};
```

Stores key-value pairs.

---

### Function

```javascript
function greet(){
    console.log("Hello");
}
```

A reusable block of code.

---

## 5. typeof Operator

Returns the data type of a value.

Example

```javascript
typeof "Hello"
```

Returns

```
string
```

Example

```javascript
typeof 20
```

Returns

```
number
```

---

## 6. Comparison Operators

Used to compare two values.

| Operator | Meaning |
|----------|---------|
| `==` | Equal (value only) |
| `===` | Strict Equal (value + type) |
| `!=` | Not Equal |
| `!==` | Strict Not Equal |
| `<` | Less Than |
| `>` | Greater Than |
| `<=` | Less Than or Equal |
| `>=` | Greater Than or Equal |

Example

```javascript
console.log(num1 <= num2);
```

---

## 7. Conditional Statements

### if

Runs code only if the condition is true.

```javascript
if(num1 < num2){
    console.log("I won");
}
```

---

### if...else

```javascript
if(num1 < num2){
    console.log("I won");
}else{
    console.log("You lose");
}
```

---

### if...else if...else

```javascript
if(num1 < num2){
    console.log("I won");
}
else if(num1 > num2){
    console.log("You lose");
}
else{
    console.log("Equal");
}
```

---

## 8. null vs undefined

```javascript
console.log(null === undefined);
```

Output

```
false
```

Explanation

- `null` means intentionally empty.
- `undefined` means value not assigned.

---

## 9. Arrays

Arrays store multiple values inside one variable.

Example

```javascript
let arr = [
    1,
    "Name",
    3.6,
    true,
    false,
    null,
    undefined,
    [2,4,5]
];
```

Arrays can contain:

- Numbers
- Strings
- Booleans
- Null
- Undefined
- Objects
- Nested Arrays

---

## 10. Array Length

Returns the number of elements.

```javascript
arr.length
```

---

## 11. Last Index

```javascript
let lastIndex = arr.length - 1;
```

Since indexing starts from **0**, the last element is always:

```
length - 1
```

---

## 12. push()

Adds an element to the end of an array.

```javascript
arr.push(6);
```

Before

```
[1,2,3]
```

After

```
[1,2,3,6]
```

---

## 13. pop()

Removes the last element.

```javascript
arr.pop();
```

Before

```
[1,2,3,6]
```

After

```
[1,2,3]
```

---

## 14. Accessing Array Elements

```javascript
arr[0]
```

First element.

```javascript
arr[arr.length - 1]
```

Last element.

---

## 15. Updating Array Elements

Arrays are mutable.

Example

```javascript
arr[3] = 18;
```

Changes the value at index **3**.

---

Example

```javascript
arr[0] = "Myname Is name";
```

Updates the first element.

---

## 16. console.log()

Displays output in the browser console.

Example

```javascript
console.log(arr);
```

Useful for:

- Debugging
- Viewing variables
- Checking array contents
- Testing code

---

# JavaScript Methods Used

### `console.log()`

Prints output.

---

### `typeof`

Returns the data type.

---

### `push()`

Adds an element to the end.

---

### `pop()`

Removes the last element.

---

### `.length`

Returns the number of elements.

---

# HTML Elements Used

- `<html>`
- `<head>`
- `<meta>`
- `<title>`
- `<body>`
- `<h2>`
- `<script>`

---

# Key Takeaways

- JavaScript can be placed in external `.js` files.
- Variables are declared using `let`, `const`, and `var`.
- JavaScript supports many data types.
- Arrays can store different types of values together.
- `push()` adds items, while `pop()` removes the last item.
- `.length` returns the number of elements.
- Conditional statements control program flow.
- `console.log()` helps debug programs.
- `typeof` identifies the type of a variable.

---

# Source Code

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <h2>Hi there..!!</h2>
</body>

<script src="index.js"></script>
</html>
```

---

## JavaScript

```javascript
let num1 = 20;
let num2 = 20;

let arr = [1, "Name", 3.6, true, false, null, undefined, [2,4,5]];

let lastIndex = arr.length - 1;

console.log(lastIndex);

console.log(arr.length);

arr.push(6);

console.log(arr);

arr.pop();

console.log(arr);

console.log(arr[arr.length - 1]);

arr[3] = 18;

console.log(arr);

arr[0] = "Myname Is name";

console.log(arr);
```

---

# Tags

- [[JavaScript]]
- [[Variables]]
- [[let]]
- [[const]]
- [[var]]
- [[Data Types]]
- [[String]]
- [[Number]]
- [[Boolean]]
- [[Null]]
- [[Undefined]]
- [[Object]]
- [[Array]]
- [[Function]]
- [[typeof]]
- [[Comparison Operators]]
- [[Equality Operators]]
- [[Conditional Statements]]
- [[if Statement]]
- [[else Statement]]
- [[else if]]
- [[Arrays]]
- [[Array Methods]]
- [[push()]]
- [[pop()]]
- [[Array Length]]
- [[Array Index]]
- [[console.log()]]
- [[External JavaScript]]
- [[Script Tag]]
- [[HTML]]
- [[Day 8]]