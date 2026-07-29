# HTML & CSS Product Page Notes (Exercise 3)

## Overview

This exercise builds a simple Amazon-style product page using HTML and CSS. It introduces **headings**, **hyperlinks that open in a new tab**, **inline CSS**, **internal CSS**, and styling buttons with reusable CSS classes.

---

# Complete HTML Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercise-3</title>

    <style>
        .amazon{
            background-color: rgb(255, 216, 20);
            color: black;
            border: none;
            border-radius: 30px;
            width: 165px;
            height: 50px;
            font-size: large;
        }

        .amazon2{
            background-color: rgb(255, 164, 28);
            color: black;
            border: none;
            border-radius: 30px;
            width: 165px;
            height: 50px;
            font-size: large;
        }
    </style>
</head>

<body>

    <a
        href="https://www.amazon.in/"
        target="_blank"
        style="color: rgb(0,113,133); font-size: large;">
        Back to Amazon
    </a>

    <h1>Nike Black Running Shoes</h1>

    <h2>$39 - in stock</h2>

    <p>Free delivery tomorrow</p>

    <br>

    <button class="amazon">
        Add to Cart
    </button>

    <button class="amazon2">
        Buy now
    </button>

</body>
</html>
```

---

# HTML Tags Used

## [[a]]

Creates a hyperlink.

```html
<a href="https://www.amazon.in/">
    Back to Amazon
</a>
```

---

## [[h1]]

Creates the main heading of a webpage.

```html
<h1>Nike Black Running Shoes</h1>
```

- Largest heading.
    
- Used for the most important title on a page.
    

---

## [[h2]]

Creates a second-level heading.

```html
<h2>$39 - in stock</h2>
```

Headings range from:

- `h1`
    
- `h2`
    
- `h3`
    
- `h4`
    
- `h5`
    
- `h6`
    

where `h1` is the largest and `h6` is the smallest.

---

## [[p]]

Creates a paragraph.

```html
<p>Free delivery tomorrow</p>
```

---

## [[button]]

Creates a clickable button.

```html
<button>Add to Cart</button>
```

---

## [[Style]]

Contains Internal CSS.

```html
<style>
    ...
</style>
```

---

## [[br]]

Creates a line break.

```html
<br>
```

---

# HTML Attributes Used

## [[href]]

Specifies the destination of a hyperlink.

```html
href="https://www.amazon.in/"
```

---

## [[target]]

Controls where a hyperlink opens.

```html
target="_blank"
```

### Common values

|Value|Meaning|
|---|---|
|`_self`|Opens in the same tab (default)|
|`_blank`|Opens in a new tab|
|`_parent`|Opens in the parent frame|
|`_top`|Opens in the full browser window|

---

## [[Style]]

Applies Inline CSS directly to an HTML element.

Example:

```html
style="color: rgb(0,113,133);"
```

---

## [[Class]]

Assigns a CSS class to an HTML element.

```html
<button class="amazon">
```

The browser applies styles from

```css
.amazon{
    ...
}
```

---

# CSS Selectors Used

## [[Class Selector]]

Selects all elements with a specific class.

```css
.amazon{
    ...
}
```

---

# CSS Properties Used

## [[Background-color]]

Sets the background color.

```css
background-color: rgb(255,216,20);
```

---

## [[color]]

Changes the text color.

Examples:

```css
color: black;
color: rgb(0,118,0);
color: rgb(0,113,133);
```

---

## [[Border]]

Controls the border.

```css
border: none;
```

---

## [[border-radius]]

Rounds the corners.

```css
border-radius: 30px;
```

---

## [[width]]

Defines the width.

```css
width: 165px;
```

---

## [[height]]

Defines the height.

```css
height: 50px;
```

---

## [[font-size]]

Changes text size.

Examples:

```css
font-size: large;
font-size: x-large;
```

---

# CSS Functions Used

## [[rgb()]]

Creates colors using Red, Green and Blue values.

Format:

```css
rgb(red, green, blue)
```

Examples:

```css
rgb(255,216,20)
rgb(255,164,28)
rgb(0,118,0)
rgb(0,113,133)
```

---

# HTML Heading Hierarchy

```text
h1  ← Main page title
│
├── h2
│   ├── h3
│   │   ├── h4
│   │   │   ├── h5
│   │   │   │   └── h6
```

Only one `h1` should normally be used for the main topic of a webpage.

---

# Concepts Learned

- [[HTML]]
    
- [[CSS]]
    
- [[Internal CSS]]
    
- [[Inline CSS]]
    
- [[Heading]]
    
- [[h1]]
    
- [[h2]]
    
- [[Paragraph]]
    
- [[Hyperlink]]
    
- [[Anchor Tag]]
    
- [[button]]
    
- [[Style Tag]]
    
- [[Class]]
    
- [[Class Selector]]
    
- [[Target Attribute]]
    
- [[Background Color]]
    
- [[Text Color]]
    
- [[Border]]
    
- [[Border Radius]]
    
- [[width]]
    
- [[height]]
    
- [[Font Size]]
    
- [[rgb()]]
    

---

# How the Link Works

```text
<a>
│
├── href
│      │
│      ▼
│  Destination URL
│
└── target="_blank"
       │
       ▼
Opens in a new browser tab
```

---

# How HTML Connects to CSS

```text
HTML
│
├── <button class="amazon">
│
▼
class="amazon"
│
▼
CSS
│
└── .amazon{
        background-color: rgb(...);
        border-radius: 30px;
        ...
    }
│
▼
Styled Button
```

---

# Key Takeaways

- `h1` defines the main heading of a webpage.
    
- `h2` defines a secondary heading.
    
- The `target="_blank"` attribute opens hyperlinks in a new browser tab.
    
- `href` specifies the destination URL.
    
- The `style` attribute applies Inline CSS.
    
- CSS classes allow reusable styling for multiple elements.
    
- `background-color`, `color`, `border`, and `border-radius` are commonly used to style buttons.
    
- `rgb()` creates colors using red, green, and blue values.
    
- Headings improve both the visual structure and semantic meaning of a webpage.