# HTML & CSS Layout Notes (Cards and Flexbox)

## Overview

This exercise introduces **page layout** using HTML and CSS. It demonstrates creating a card component, displaying images, linking external websites, using **Flexbox** for navigation layout, applying spacing, borders, colors, and connecting an external CSS file.

---

# Complete HTML Code

> **Note:** The code below is identical to your exercise except the long image URL has been shortened with `...` for readability.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <link rel="stylesheet" href="index.css">
</head>

<body>

    <div style="border:1px solid gray; width:25%; margin:auto; text-align:center; border-radius:10px; background-color:#f0f0f0; color:blue;">

        <img
            height="240px"
            width="320px"
            src="https://..."
            alt="logo">

        <h3>
            <a href="https://www.ibm.com/in-en" target="_blank">
                IBM logo
            </a>
        </h3>

        <p>
            IBM logo in black theme...
            <span>doloremque delectus</span>
        </p>

    </div>

    <div style="border:1px solid none; width:100%; margin:auto; padding:10px; display:flex; justify-content:space-evenly; align-items:center;">

        <div>Nav Link</div>
        <div>Nav Link</div>
        <div>Nav Link</div>
        <div>Nav Link</div>
        <div>Nav Link</div>

    </div>

</body>
</html>
```

---

# HTML Tags Used

## [[link]]

Links external resources to an HTML document.

Example:

```html
<link rel="stylesheet" href="index.css">
```

Most commonly used to connect external CSS files.

---

## [[div]]

Creates a container.

```html
<div>

</div>
```

Used for:

- Grouping elements
    
- Creating layouts
    
- Applying CSS
    
- Building cards
    
- Navigation bars
    

---

## [[img]]

Displays an image.

```html
<img
    src="image.png"
    alt="Logo">
```

---

## [[a]]

Creates a hyperlink.

```html
<a href="https://www.ibm.com">
    IBM
</a>
```

---

## [[h3]]

Creates a third-level heading.

```html
<h3>IBM Logo</h3>
```

---

## [[p]]

Creates a paragraph.

```html
<p>Lorem ipsum...</p>
```

---

## [[span]]

Creates an inline container.

```html
<span>Highlighted Text</span>
```

Unlike `div`, `span` does **not** start on a new line.

It is mainly used to style part of a sentence.

Example:

```html
<p>
    Hello
    <span>World</span>
</p>
```

---

# HTML Attributes Used

## [[rel]]

Defines the relationship between the current document and the linked resource.

```html
rel="stylesheet"
```

Meaning:

- The linked file is a stylesheet.
    

---

## [[href]]

Specifies the destination.

Examples:

```html
href="index.css"
```

```html
href="https://www.ibm.com"
```

---

## [[src]]

Specifies the image location.

```html
src="image.png"
```

---

## [[alt]]

Alternative text for images.

```html
alt="IBM Logo"
```

---

## [[target]]

Controls where hyperlinks open.

```html
target="_blank"
```

Opens the webpage in a new browser tab.

---

# CSS Properties Used

## [[border]]

Creates a border.

```css
border: 1px solid gray;
```

Syntax:

```css
border:
width
style
color;
```

---

## [[width]]

Sets the width.

```css
width: 25%;
```

Percentage values are relative to the parent element.

---

## [[height]]

Sets the height.

```css
height: 240px;
```

---

## [[margin]]

Creates space **outside** an element.

Example:

```css
margin: auto;
```

`auto` horizontally centers block elements.

---

## [[padding]]

Creates space **inside** an element.

```css
padding: 10px;
```

Difference:

```text
Margin
┌──────────────────┐
│                  │
│  Border          │
│  ┌────────────┐  │
│  │ Padding    │  │
│  │ ┌────────┐ │  │
│  │ │Content │ │  │
│  │ └────────┘ │  │
│  └────────────┘  │
└──────────────────┘
```

---

## [[text-align]]

Aligns text.

```css
text-align: center;
```

Possible values:

- left
    
- center
    
- right
    
- justify
    

---

## [[border-radius]]

Rounds corners.

```css
border-radius: 10px;
```

---

## [[background-color]]

Sets the background color.

```css
background-color: #f0f0f0;
```

---

## [[color]]

Changes text color.

```css
color: blue;
```

---

# Flexbox Properties

## [[display]]

Defines how an element is displayed.

```css
display: flex;
```

This turns the element into a **Flex Container**.

---

## [[Flexbox]]

Flexbox is a CSS layout system for arranging items efficiently.

```css
display: flex;
```

After enabling Flexbox, child elements become **Flex Items**.

---

## [[justify-content]]

Controls alignment along the **main axis**.

```css
justify-content: space-evenly;
```

Common values:

- flex-start
    
- center
    
- flex-end
    
- space-between
    
- space-around
    
- space-evenly
    

Example:

```text
space-evenly

□     □     □     □
```

---

## [[align-items]]

Controls alignment along the **cross axis**.

```css
align-items: center;
```

Common values:

- flex-start
    
- center
    
- flex-end
    
- stretch
    

---

# CSS Color Formats

## [[Hex Color]]

Uses hexadecimal values.

Example:

```css
background-color: #f0f0f0;
```

Format:

```css
#RRGGBB
```

Example:

```css
#ffffff
#000000
#3498db
```

---

## [[Color Keywords]]

Named colors.

Examples:

```css
color: blue;
background-color: aquamarine;
background-color: gray;
```

---

# External CSS

Instead of writing CSS inside `<style>`:

```html
<style>
...
</style>
```

you can place it inside another file:

```css
index.css
```

and connect it using

```html
<link
    rel="stylesheet"
    href="index.css">
```

This keeps HTML cleaner and makes CSS reusable across multiple pages.

---

# Concepts Learned

- [[HTML]]
    
- [[CSS]]
    
- [[External CSS]]
    
- [[Link Tag]]
    
- [[Div]]
    
- [[span]]
    
- [[Image]]
    
- [[Hyperlink]]
    
- [[Card Layout]]
    
- [[Flexbox]]
    
- [[Flex Container]]
    
- [[Flex Item]]
    
- [[display]]
    
- [[Justify Content]]
    
- [[Align Items]]
    
- [[margin]]
    
- [[padding]]
    
- [[Border]]
    
- [[Border Radius]]
    
- [[Text Align]]
    
- [[Width]]
    
- [[Height]]
    
- [[Background Color]]
    
- [[Hex Color]]
    
- [[Color Keywords]]
    

---

# Flexbox Layout

```text
Flex Container
│
├── Item 1
├── Item 2
├── Item 3
├── Item 4
└── Item 5
```

With

```css
display: flex;
justify-content: space-evenly;
align-items: center;
```

the items are evenly spaced horizontally and vertically centered.

---

# Key Takeaways

- `div` is the primary container element used for layouts.
    
- `span` styles inline text without creating a new line.
    
- The `<link>` tag connects external CSS files.
    
- `display: flex` activates the Flexbox layout system.
    
- `justify-content` controls horizontal spacing of flex items.
    
- `align-items` controls vertical alignment of flex items.
    
- `margin` creates space outside an element, while `padding` creates space inside.
    
- `border-radius` creates rounded corners.
    
- Hex colors (`#f0f0f0`) and named colors (`blue`, `gray`, `aquamarine`) are alternative ways to specify colors.
    
- Separating HTML and CSS into different files improves maintainability and organization.