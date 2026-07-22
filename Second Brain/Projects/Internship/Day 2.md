# HTML Resume Page Notes

## Overview

This exercise demonstrates how to build a simple resume webpage using only HTML. It introduces page structure, headings, paragraphs, horizontal rules, lists, text formatting, and element attributes to organize professional information.

---

# Complete HTML Code

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resume</title>
</head>

<body>

    <h1 align="center">Harananda Loukrakpam</h1>

    <p align="center">
        699 Emard Islands, Los Angeles, CA • +1 (555) 196-3763
    </p>

    <hr>

    <h2 align="center">WORK EXPERIENCE</h2>

    <hr>

    <h3>SENIOR .NET / HTML DEVELOPER</h3>

    <p><b>Location:</b> Dallas, TX</p>

    <p><b>Duration:</b> 06/2017 - PRESENT</p>

    <ul>
        <li>...</li>
    </ul>

    <hr>

    <h3>HTML DEVELOPER</h3>

    <p><b>Location:</b> Dallas, TX</p>

    <p><b>Duration:</b> 01/2012 - 05/2017</p>

    <ul>
        <li>...</li>
    </ul>

    <hr>

    <h3>JUNIOR HTML DEVELOPER</h3>

    <p><b>Location:</b> Detroit, MI</p>

    <p><b>Duration:</b> 10/2005 - 08/2011</p>

    <ul>
        <li>...</li>
    </ul>

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

The root element that contains the entire webpage.

```html
<html lang="en">
```

---

## [[head]]

Contains metadata about the webpage.

```html
<head>
    ...
</head>
```

---

## [[meta]]

Provides information about the webpage.

Examples:

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

Defines the text shown on the browser tab.

```html
<title>Resume</title>
```

---

## [[body]]

Contains everything visible on the webpage.

```html
<body>
    ...
</body>
```

---

## [[h1]]

Creates the primary heading.

```html
<h1>Harananda Loukrakpam</h1>
```

Usually used for the page title.

---

## [[h2]]

Creates a second-level heading.

```html
<h2>WORK EXPERIENCE</h2>
```

Used for major sections.

---

## [[h3]]

Creates a third-level heading.

```html
<h3>SENIOR .NET / HTML DEVELOPER</h3>
```

Useful for subsection titles.

---

## [[p]]

Creates a paragraph.

```html
<p>Location: Dallas, TX</p>
```

---

## [[b]]

Makes text bold.

```html
<b>Location:</b>
```

Displays:

**Location:**

---

## [[ul]]

Creates an unordered (bulleted) list.

```html
<ul>
    <li>Item</li>
</ul>
```

---

## [[li]]

Represents an individual list item.

```html
<li>Creating modern interfaces.</li>
```

---

## [[hr]]

Creates a horizontal rule (horizontal line).

```html
<hr>
```

Used to visually separate sections.

---

# HTML Attributes Used

## [[lang]]

Specifies the language of the document.

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

Helps webpages display correctly on different screen sizes.

```html
content="width=device-width, initial-scale=1.0"
```

---

## [[align]]

Aligns the content of certain HTML elements.

Example:

```html
<h1 align="center">
```

or

```html
<p align="center">
```

Possible values:

- `left`
    
- `center`
    
- `right`
    

> **Note:** The `align` attribute is **deprecated** in HTML5. Modern webpages use [[CSS]] instead.

Example using CSS:

```css
text-align: center;
```

---

# Text Formatting Tags

## [[Bold Text]]

Using the `<b>` tag.

```html
<b>Duration:</b>
```

Output:

**Duration:**

---

# Document Structure

```text
Resume
│
├── Name (h1)
│
├── Contact Information (p)
│
├── Horizontal Rule
│
├── Work Experience (h2)
│
├── Horizontal Rule
│
├── Job Title (h3)
│   ├── Location
│   ├── Duration
│   └── Responsibilities (ul)
│
├── Horizontal Rule
│
├── Job Title (h3)
│   ├── Location
│   ├── Duration
│   └── Responsibilities
│
└── Job Title (h3)
    ├── Location
    ├── Duration
    └── Responsibilities
```

---

# Resume Hierarchy

```text
Resume
│
├── Personal Information
│
├── Work Experience
│   ├── Job 1
│   ├── Job 2
│   └── Job 3
│
└── Responsibilities
```

---

# Concepts Learned

- [[HTML]]
    
- [[HTML Document Structure]]
    
- [[DOCTYPE]]
    
- [[Head]]
    
- [[Body]]
    
- [[Meta Tag]]
    
- [[Title]]
    
- [[Heading]]
    
- [[h1]]
    
- [[h2]]
    
- [[h3]]
    
- [[Paragraph]]
    
- [[Bold Text]]
    
- [[Horizontal Rule]]
    
- [[Unordered List]]
    
- [[List Item]]
    
- [[Attributes]]
    
- [[Align Attribute]]
    
- [[Character Encoding]]
    
- [[Viewport]]
    
- [[Semantic HTML]]
    
- [[Resume Layout]]
    

---

# Key Takeaways

- `h1`, `h2`, and `h3` create a clear heading hierarchy.
    
- `<p>` displays paragraphs of text.
    
- `<b>` makes text bold for emphasis.
    
- `<ul>` and `<li>` organize information into readable bullet points.
    
- `<hr>` visually separates sections of a webpage.
    
- The `align` attribute can center content but is **deprecated**; modern websites use `text-align` in CSS instead.
    
- Well-structured HTML improves readability and accessibility before any CSS styling is added.