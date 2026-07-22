# HTML Product Page Notes (Exercise 1)

## Overview

This exercise introduces the basic HTML elements used to build a simple product page similar to an online shopping website. It demonstrates how to create hyperlinks, paragraphs, and buttons without using CSS.

---

# Complete HTML Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercise-1</title>
</head>
<body>
    <a href="https://www.amazon.in/">Back to Amazon</a>

    <p style="font-weight: bold;">Nike Black Running Shoes</p>

    <p>$39 - in stock</p>

    <p>Free Delivery Tomorrow</p>

    <button>Add to Cart</button>

    <button>Buy now</button>
</body>
</html>
```

---

# HTML Tags Used

## [[]]

Declares that the document uses **HTML5**.

```html
<!DOCTYPE html>
```

It tells the browser how to interpret the document.

---

## [[html]]

The root element that contains the entire webpage.

```html
<html lang="en">
    ...
</html>
```

### Attribute

#### [[lang]]

Specifies the language of the webpage.

```html
lang="en"
```

- `en` = English
    
- Helps browsers and search engines understand the page language.
    

---

## [[head]]

Contains information **about** the webpage that is **not displayed** on the page.

```html
<head>
    ...
</head>
```

Common contents:

- `title`
    
- `meta`
    
- `link`
    
- `style`
    
- `script`
    

---

## [[meta]]

Provides metadata (information about the webpage).

### [[charset]]

Defines the character encoding.

```html
<meta charset="UTF-8">
```

`UTF-8` supports most characters and symbols used around the world.

---

### [[viewport]]

Controls how the webpage appears on different screen sizes.

```html
<meta
    name="viewport"
    content="width=device-width, initial-scale=1.0">
```

Meaning:

- `width=device-width` → Match the screen width.
    
- `initial-scale=1.0` → Display at normal zoom.
    

This is essential for **responsive web design**.

---

## [[title]]

Sets the title displayed on the browser tab.

```html
<title>Exercise-1</title>
```

This text does **not** appear inside the webpage.

---

## [[body]]

Contains everything visible on the webpage.

```html
<body>
    ...
</body>
```

Examples:

- Text
    
- Images
    
- Buttons
    
- Links
    
- Videos
    
- Forms
    

---

## [[a]]

Creates a hyperlink.

```html
<a href="https://www.amazon.in/">
    Back to Amazon
</a>
```

### Attribute

#### [[href]]

Specifies the destination URL.

```html
href="https://www.amazon.in/"
```

When clicked, the browser navigates to the specified webpage.

---

## [[p]]

Creates a paragraph.

```html
<p>Nike Black Running Shoes</p>
```

Paragraphs automatically start on a new line and include default spacing.

---

## [[button]]

Creates a clickable button.

```html
<button>Add to Cart</button>
```

Another example:

```html
<button>Buy now</button>
```

Buttons can later be styled using [[CSS]] and can execute actions using [[JavaScript]].

---

# HTML Attributes Used

## [[style]]

Applies CSS directly to an HTML element (called **Inline CSS**).

Example:

```html
<p style="font-weight: bold;">
    Nike Black Running Shoes
</p>
```

This makes the paragraph bold without creating a separate CSS file.

---

## [[font-weight]]

A CSS property that controls text thickness.

```css
font-weight: bold;
```

Possible values:

- normal
    
- bold
    
- 100–900
    

---

# Concepts Learned

- [[HTML]]
    
- [[HTML Document Structure]]
    
- [[DOCTYPE]]
    
- [[head]]
    
- [[body]]
    
- [[Meta Tag]]
    
- [[Character Encoding]]
    
- [[viewport]]
    
- [[title]]
    
- [[Hyperlink]]
    
- [[Anchor Tag]]
    
- [[Paragraph]]
    
- [[Button]]
    
- [[Attributes]]
    
- [[Inline CSS]]
    
- [[Font Weight]]
    
- [[Responsive Web Design]]
    

---

# Page Structure

```
HTML Document
│
├── <!DOCTYPE html>
│
├── html
│   │
│   ├── head
│   │   ├── meta (charset)
│   │   ├── meta (viewport)
│   │   └── title
│   │
│   └── body
│       ├── a
│       ├── p
│       ├── p
│       ├── p
│       ├── button
│       └── button
```

---

# Key Takeaways

- Every HTML page begins with `<!DOCTYPE html>`.
    
- The `<html>` element contains the entire webpage.
    
- The `<head>` stores information about the page, while the `<body>` contains visible content.
    
- The `<a>` tag creates clickable hyperlinks using the `href` attribute.
    
- The `<p>` tag displays paragraphs of text.
    
- The `<button>` tag creates clickable buttons.
    
- The `style` attribute applies CSS directly to an element (Inline CSS).
    
- `font-weight: bold` makes text appear bold.
    
- The viewport meta tag helps webpages display correctly on phones, tablets, and desktops.