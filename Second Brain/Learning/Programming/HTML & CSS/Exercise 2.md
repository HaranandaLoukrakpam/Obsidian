# HTML & CSS Button Styling Notes (Exercise 2)

## Overview

This exercise introduces **Internal CSS** by styling buttons to resemble those found on popular websites such as **Uber**, **Amazon**, **GitHub**, **Bootstrap**, and **LinkedIn**. It demonstrates how HTML elements connect to CSS classes to create visually appealing user interfaces.

---

# Complete HTML Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exercise-2</title>

    <style>
        .uber{
            background-color: black;
            color: white;
            border: none;
            height: 50px;
            width: 145px;
            font-weight: bold;
            font-family: sans-serif;
            font-size: medium;
        }

        .amazon{
            background-color: rgb(255, 216, 20);
            color: black;
            border: none;
            border-radius: 30px;
            width: 165px;
            height: 50px;
            font-size: medium;
        }

        .github{
            background-color: rgb(46, 164, 79);
            color: white;
            border: none;
            border-radius: 3px;
            width: 110px;
            height: 50px;
            font-weight: bold;
            font-size: large;
        }

        .bootstrap1{
            background-color: rgb(121, 82, 179);
            color: white;
            font-size: medium;
            border: none;
            border-radius: 3px;
            height: 50px;
            width: 120px;
            font-weight: bold;
        }

        .bootstrap2{
            color: rgb(121, 82, 179);
            background-color: transparent;
            font-size: medium;
            border: 1px solid rgb(121, 82, 179);
            border-radius: 3px;
            height: 50px;
            width: 110px;
            font-weight: bold;
        }

        .linkedin1{
            background-color: rgb(10, 102, 194);
            color: white;
            font-size: medium;
            border: none;
            border-radius: 30px;
            height: 50px;
            width: 255px;
            font-weight: bold;
        }

        .linkedin2{
            color: rgb(10, 102, 194);
            background-color: transparent;
            font-size: medium;
            border: 1px solid rgb(10, 102, 194);
            border-radius: 30px;
            height: 50px;
            width: 110px;
            font-weight: bold;
        }
    </style>
</head>

<body>

    <button class="uber">Request now</button>
    <button class="amazon">Add to Cart</button>
    <button class="github">Sign up</button>

    <br><br>

    <button class="bootstrap1">Get started</button>
    <button class="bootstrap2">Download</button>

    <br><br>

    <button class="linkedin1">Apply on company website</button>
    <button class="linkedin2">Save</button>

</body>
</html>
```

---

# HTML Tags Used

## [[style]]

Defines **Internal CSS**.

```html
<style>
    /* CSS goes here */
</style>
```

Everything inside the `<style>` tag is interpreted as CSS.

---

## [[button]]

Creates a clickable button.

```html
<button>Click Me</button>
```

Buttons can be styled using CSS classes.

---

## [[br]]

Creates a line break.

```html
<br>
```

This exercise uses:

```html
<br><br>
```

to insert extra vertical spacing between groups of buttons.

---

# HTML Attributes Used

## [[class]]

Assigns a CSS class to an HTML element.

```html
<button class="amazon">
    Add to Cart
</button>
```

The browser searches for a matching CSS selector.

```css
.amazon{
    ...
}
```

---

# CSS Selectors Used

## [[Class Selector]]

A class selector begins with a period (`.`).

```css
.amazon{
    ...
}
```

Every HTML element with

```html
class="amazon"
```

will receive these styles.

---

# CSS Properties Used

## [[background-color]]

Changes the background color.

```css
background-color: black;
```

Examples:

```css
background-color: rgb(255,216,20);
background-color: transparent;
```

---

## [[color]]

Changes the text color.

```css
color: white;
```

---

## [[border]]

Defines the border.

```css
border: none;
```

or

```css
border: 1px solid rgb(121,82,179);
```

Syntax:

```css
border: width style color;
```

---

## [[border-radius]]

Rounds the corners.

```css
border-radius: 30px;
```

Large values create pill-shaped buttons.

---

## [[width]]

Sets the width.

```css
width: 165px;
```

---

## [[height]]

Sets the height.

```css
height: 50px;
```

---

## [[font-size]]

Controls text size.

```css
font-size: medium;
```

Examples:

- small
    
- medium
    
- large
    
- 18px
    
- 2rem
    

---

## [[font-weight]]

Controls text thickness.

```css
font-weight: bold;
```

Other values:

```css
font-weight: normal;
font-weight: 400;
font-weight: 700;
```

---

## [[font-family]]

Changes the font.

```css
font-family: sans-serif;
```

Other examples:

```css
font-family: Arial;
font-family: Verdana;
font-family: serif;
font-family: monospace;
```

---

# CSS Functions Used

## [[rgb()]]

Creates colors using Red, Green and Blue values.

Format:

```css
rgb(red, green, blue)
```

Each value ranges from **0–255**.

Examples:

```css
rgb(255,216,20)
rgb(46,164,79)
rgb(121,82,179)
rgb(10,102,194)
```

---

# CSS Color Keywords

## [[Transparent]]

Makes the background transparent.

```css
background-color: transparent;
```

The element becomes see-through, allowing the parent background to show through.

---

# Concepts Learned

- [[HTML]]
    
- [[CSS]]
    
- [[Internal CSS]]
    
- [[Style Tag]]
    
- [[Button]]
    
- [[Class]]
    
- [[Class Selector]]
    
- [[Background Color]]
    
- [[Text Color]]
    
- [[Border]]
    
- [[Border Radius]]
    
- [[Width]]
    
- [[Height]]
    
- [[Font Size]]
    
- [[Font Weight]]
    
- [[Font Family]]
    
- [[rgb()]]
    
- [[Transparent]]
    
- [[User Interface (UI)]]
    
- [[Button Styling]]
    

---

# How HTML and CSS Work Together

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
        background-color: rgb(255,216,20);
        border-radius: 30px;
        ...
    }
│
▼
Styled Button
```

---

# Key Takeaways

- HTML provides the **structure** of a webpage.
    
- CSS controls the **appearance** of HTML elements.
    
- The `class` attribute connects HTML elements to CSS rules.
    
- The `<style>` tag contains Internal CSS.
    
- `background-color` changes an element's background.
    
- `color` changes the text color.
    
- `border` customizes or removes borders.
    
- `border-radius` rounds corners.
    
- `font-family` changes the font.
    
- `font-size` changes text size.
    
- `font-weight` changes text thickness.
    
- `rgb()` creates colors using Red, Green, and Blue values.
    
- `transparent` removes the background color while keeping the element visible.