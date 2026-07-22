Tags: [[HTML]],[[CSS]],[[Frontend]],[[Full-Stack Development]],[[Web Developments]].

HTML (HyperText Markup Language) and CSS (Cascading Style Sheets) are the two foundational languages of the World Wide Web. If you think of a webpage as a house, HTML is the framing and bricks—the structural foundation—while CSS is the paint, interior design, and landscaping that makes it look good.

Here is a detailed breakdown of how both languages work and how they interact.

## Part 1: HTML (The Structure)

HTML is not a programming language; it is a **markup language**. It uses "tags" to wrap around content, telling the web browser what that content is (e.g., "this is a paragraph," "this is an image," "this is a link").

### Basic Syntax

HTML consists of elements, which are usually made up of an opening tag, the content, and a closing tag.

HTML

```
<p>This is a paragraph of text.</p>
```

- **`<p>`**: The opening tag.
    
- **`This is a paragraph of text.`**: The content.
    
- **`</p>`**: The closing tag (indicated by the forward slash).
    

Tags can also have **attributes**, which provide extra information about the element. Attributes always go in the opening tag.

HTML

```
<a href="https://google.com">Click here to search</a>
```

_(Here, `href` is the attribute telling the link where to go)._

### The HTML Boilerplate

Every valid HTML document requires a specific structure to be recognized correctly by a browser:

HTML

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My First Webpage</title>
</head>
<body>
    <!-- Everything visible on the page goes here -->
    <h1>Welcome to my site</h1>
</body>
</html>
```

- **`<!DOCTYPE html>`**: Tells the browser to expect modern HTML5.
    
- **`<html>`**: The root element wrapping all content.
    
- **`<head>`**: Contains metadata (info _about_ the page), like the title on the browser tab, links to CSS files, and character encoding. It is invisible to the user.
    
- **`<body>`**: Contains all the visible content of the webpage.
    

### Semantic HTML

Modern HTML5 introduced "semantic" tags. Instead of using generic containers (like `<div>`) for everything, we use tags that describe their purpose. This is crucial for accessibility (screen readers) and SEO (Search Engine Optimization).

- **`<header>`**: Introductory content or logos.
    
- **`<nav>`**: The main navigation menu.
    
- **`<main>`**: The primary content of the page.
    
- **`<article>`**: A self-contained piece of content (like a blog post).
    
- **`<footer>`**: Copyright info, links, and closing content at the bottom.
    

## Part 2: CSS (The Presentation)

CSS dictates how HTML elements are displayed on the screen. It controls colors, fonts, spacing, sizing, and layout.

### How to Apply CSS

There are three ways to apply CSS to HTML, but **External** is the industry standard because it keeps your structure and styling neatly separated.

1. **Inline:** Directly inside the HTML tag using the `style` attribute (Avoid this unless necessary).
    
2. **Internal:** Inside a `<style>` block in the HTML `<head>`.
    
3. **External:** In a separate `.css` file linked in the `<head>` like this: `<link rel="stylesheet" href="styles.css">`.
    

### Basic Syntax

A CSS rule consists of a **selector** (pointing to the HTML element) and a **declaration block** (the styles to apply).

CSS

```
h1 {
    color: blue;
    font-size: 24px;
}
```

- **`h1`**: The selector (targets all `<h1>` tags).
    
- **`color: blue;`**: The declaration (`color` is the property, `blue` is the value).
    

### Common Selectors

To style specific elements without affecting everything on the page, CSS uses different selectors:

|**Selector Type**|**Syntax Example**|**What it targets**|
|---|---|---|
|**Element**|`p { ... }`|All `<p>` tags on the page.|
|**Class**|`.highlight { ... }`|Any element with `class="highlight"`. Used for styling multiple elements.|
|**ID**|`#header { ... }`|The specific element with `id="header"`. Used for unique elements (only one per page).|

### The Box Model

This is the most important concept in CSS. **Every single element in HTML is treated as a rectangular box.** The Box Model determines how big that box is and how it interacts with other boxes. From the inside out, it consists of:

1. **Content:** The actual text or image.
    
2. **Padding:** Transparent space _inside_ the box, between the content and the border.
    
3. **Border:** The line surrounding the padding and content.
    
4. **Margin:** Transparent space _outside_ the box, separating it from other elements.
    

### Layouts: Flexbox and Grid

Historically, positioning elements side-by-side in CSS was difficult. Today, we have two modern systems built right into CSS:

- **Flexbox (One-Dimensional):** Perfect for arranging items in a single row or a single column (e.g., aligning items in a navigation bar).
    
- **CSS Grid (Two-Dimensional):** Perfect for building complex, full-page layouts with both rows and columns (e.g., a photo gallery).
