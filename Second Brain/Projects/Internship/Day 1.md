# HTML Fundamentals Notes (Practice Exercise)

## Overview

This exercise introduces many of the most commonly used HTML elements. It demonstrates document structure, headings, paragraphs, hyperlinks, images, lists, user input fields, containers, and buttons. Together, these form the foundation of almost every webpage.

---

# Complete HTML Code

> **Note:** The original code contains a Base64-encoded image inside the `src` attribute. For readability, it is abbreviated below as `data:image/png;base64,...`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>

    <h1>Hello World</h1>
    <h2>My name is Alex</h2>

    <p>This is a paragraph</p>

    <a href="https://www.google.com">
        Visit Google Here
    </a>

    <a
        href="https://www.google.com"
        target="_blank">
        Visit Google Here
    </a>

    <img
        src="data:image/png;base64,..."
        alt="logo">

    <ol>
        <li>First Item</li>
        <li>Second Item</li>
    </ol>

    <ul>
        <li>First Item</li>
        <li>Second Item</li>
    </ul>

    <input type="text" placeholder="Enter your name">
    <input type="password" placeholder="Enter your password">
    <input type="email" placeholder="Enter your email">
    <input type="date">

    <div>

        <img
            src="data:image/png;base64,..."
            alt="">

        <h1>This is an IBM logo</h1>

        <p>Lorem ipsum...</p>

    </div>

    <button type="button">
        Click Here
    </button>

</body>
</html>
```

---

# HTML Tags Used

## [[]]

Declares the document as an HTML5 document.

```html
<!DOCTYPE html>
```

---

## [[html]]

The root element of every HTML document.

```html
<html lang="en">
```

---

## [[head]]

Contains metadata and information about the webpage.

```html
<head>
    ...
</head>
```

---

## [[meta]]

Provides metadata.

Example:

```html
<meta charset="UTF-8">
```

```html
<meta
    name="viewport"
    content="width=device-width, initial-scale=1.0">
```

---

## [[title]]

Specifies the browser tab title.

```html
<title>Document</title>
```

---

## [[body]]

Contains everything displayed on the webpage.

```html
<body>
    ...
</body>
```

---

## [[h1]]

Creates the main heading.

```html
<h1>Hello World</h1>
```

Usually only one main heading should exist on a webpage.

---

## [[h2]]

Creates a second-level heading.

```html
<h2>My name is Alex</h2>
```

---

## [[p]]

Creates a paragraph.

```html
<p>This is a paragraph.</p>
```

---

## [[a]]

Creates a hyperlink.

```html
<a href="https://www.google.com">
    Visit Google
</a>
```

---

## [[img]]

Displays an image.

```html
<img src="image.png" alt="Logo">
```

Unlike most HTML elements, `<img>` does **not** have a closing tag.

---

## [[ol]]

Creates an **Ordered List**.

```html
<ol>
    <li>First</li>
    <li>Second</li>
</ol>
```

Displays:

1. First
    
2. Second
    

---

## [[ul]]

Creates an **Unordered List**.

```html
<ul>
    <li>First</li>
    <li>Second</li>
</ul>
```

Displays bullet points.

---

## [[li]]

Represents an individual list item.

```html
<li>First Item</li>
```

Used inside both `ol` and `ul`.

---

## [[input]]

Creates an input field.

Examples:

```html
<input type="text">
```

```html
<input type="email">
```

`input` is a **void element**, meaning it has no closing tag.

---

## [[div]]

Creates a generic container.

```html
<div>

</div>
```

`div` has **no visual appearance** by default.

It is mainly used to:

- Group elements
    
- Apply CSS
    
- Structure layouts
    
- Organize sections
    

---

## [[button]]

Creates a clickable button.

```html
<button>Click Here</button>
```

---

# HTML Attributes Used

## [[lang]]

Defines the document language.

```html
lang="en"
```

---

## [[charset]]

Defines the character encoding.

```html
charset="UTF-8"
```

---

## [[viewport]]

Controls responsive behavior.

```html
content="width=device-width, initial-scale=1.0"
```

---

## [[href]]

Specifies the destination of a hyperlink.

```html
href="https://www.google.com"
```

---

## [[target]]

Controls where the hyperlink opens.

```html
target="_blank"
```

`_blank` opens the link in a new browser tab.

---

## [[src]]

Specifies the location of an image.

```html
src="image.png"
```

Your example uses a **Base64 Data URL** instead of an external image file.

---

## [[alt]]

Alternative text for an image.

```html
alt="Logo"
```

Used when:

- Image cannot load
    
- Screen readers describe the image
    
- Improves accessibility
    

---

## [[type]]

Defines the type of an element.

Examples:

```html
type="text"
```

```html
type="password"
```

```html
type="email"
```

```html
type="date"
```

```html
type="button"
```

---

## [[placeholder]]

Displays temporary hint text inside an input field.

```html
placeholder="Enter your name"
```

The placeholder disappears once the user starts typing.

---

# Input Types Learned

## [[Text Input]]

```html
<input type="text">
```

Accepts normal text.

---

## [[Password Input]]

```html
<input type="password">
```

Hides entered characters.

---

## [[Email Input]]

```html
<input type="email">
```

Accepts email addresses.

Browsers may perform basic validation.

---

## [[Date Input]]

```html
<input type="date">
```

Displays a date picker.

---

# List Types

## [[Ordered List]]

Uses numbers.

```html
<ol>
```

---

## [[Unordered List]]

Uses bullets.

```html
<ul>
```

---

# Image Sources

Your code uses

```html
src="data:image/png;base64,..."
```

This is called a **[[Data URL]]** or **[[Base64 Image]]**.

Instead of loading an image from a file:

```html
<img src="logo.png">
```

the image data is stored directly inside the HTML document.

---

# Concepts Learned

- [[HTML]]
    
- [[HTML Document Structure]]
    
- [[DOCTYPE]]
    
- [[Head]]
    
- [[Body]]
    
- [[Meta Tag]]
    
- [[Heading]]
    
- [[Paragraph]]
    
- [[Hyperlink]]
    
- [[Anchor Tag]]
    
- [[Image]]
    
- [[Data URL]]
    
- [[Base64 Image]]
    
- [[Ordered List]]
    
- [[Unordered List]]
    
- [[List Item]]
    
- [[input]]
    
- [[Text Input]]
    
- [[Password Input]]
    
- [[Email Input]]
    
- [[Date Input]]
    
- [[placeholder]]
    
- [[Button]]
    
- [[Container]]
    
- [[div]]
    
- [[Attributes]]
    
- [[Responsive Web Design]]
    

---

# Page Structure

```text
HTML Document
│
├── head
│   ├── meta
│   ├── meta
│   └── title
│
└── body
    ├── h1
    ├── h2
    ├── p
    ├── a
    ├── a
    ├── img
    ├── ol
    │   └── li
    ├── ul
    │   └── li
    ├── input
    ├── input
    ├── input
    ├── input
    ├── div
    │   ├── img
    │   ├── h1
    │   └── p
    └── button
```

---

# Key Takeaways

- HTML pages are built using nested elements called **tags**.
    
- `h1`–`h6` define headings with different importance.
    
- `a` creates hyperlinks using the `href` attribute.
    
- `img` displays images using the `src` attribute.
    
- `alt` improves accessibility by describing images.
    
- `ol` creates numbered lists, while `ul` creates bulleted lists.
    
- `li` represents individual list items.
    
- `input` fields collect user data, and the `type` attribute changes their behavior.
    
- `placeholder` displays helper text inside input fields.
    
- `div` groups related elements into sections.
    
- Buttons trigger actions and can later be enhanced using [[CSS]] and [[JavaScript]].