# CSS Button Styling Notes (Basic Buttons)

## Overview

This exercise introduces the fundamentals of CSS button styling by recreating three common button styles inspired by **YouTube** and **Twitter (X)**. It covers the basics of colors, borders, rounded corners, sizing, mouse cursors, and typography.

---

# HTML Structure

```html
<button class="subscribe_button">SUBSCRIBE</button>
<button class="join_button">JOIN</button>
<button class="tweet_button">TWEET</button>
```

### Explanation

Each `button` element is assigned a unique CSS class.

```html
<button class="subscribe_button">SUBSCRIBE</button>
```

- `button` → Creates a clickable button.
    
- `class="subscribe_button"` → Applies the CSS styles defined in `.subscribe_button`.
    
- `SUBSCRIBE` → Text displayed inside the button.
    

---

# Complete CSS Code

```css
.subscribe_button{
    background-color: rgb(200, 0, 0);
    color: white;
    border: none;
    border-radius: 1.5px;
    height: 30px;
    width: 105px;
    cursor: pointer;
}

.join_button{
    background-color: white;
    border: 1px solid rgb(66, 66, 255);
    color: rgb(66, 66, 255);
    border-radius: 1.5px;
    height: 30px;
    width: 60px;
}

.tweet_button{
    background-color: rgb(42, 149, 248);
    color: white;
    border: none;
    border-radius: 30px;
    height: 30px;
    width: 72px;
    cursor: pointer;
    font-weight: bold;
}
```

---

# CSS Properties Used

## [[Background-color]]

Sets the background color of an element.

```css
background-color: rgb(200, 0, 0);
```

Examples:

```css
background-color: white;
background-color: rgb(42, 149, 248);
```

---

## [[color]]

Changes the text color.

```css
color: white;
```

Example:

```css
color: rgb(66, 66, 255);
```

---

## [[Border]]

Controls the border around an element.

```css
border: none;
```

or

```css
border: 1px solid rgb(66, 66, 255);
```

Syntax:

```css
border: width style color;
```

Example:

```css
border: 2px dashed red;
```

---

## [[border-radius]]

Rounds the corners of an element.

```css
border-radius: 1.5px;
```

Example:

```css
border-radius: 30px;
```

A large value creates a pill-shaped button.

---

## [[height]]

Sets the height of an element.

```css
height: 30px;
```

---

## [[width]]

Sets the width of an element.

```css
width: 105px;
```

---

## [[cursor]]

Changes the appearance of the mouse pointer when it hovers over an element.

```css
cursor: pointer;
```

Common values:

```css
cursor: default;
cursor: pointer;
cursor: text;
cursor: move;
cursor: not-allowed;
```

`pointer` displays a hand icon, indicating the element is clickable.

---

## [[font-weight]]

Controls the thickness of the text.

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

# CSS Functions Used

## [[rgb()]]

Defines colors using Red, Green, and Blue values.

Format:

```css
rgb(red, green, blue)
```

Each value ranges from **0 to 255**.

Examples:

```css
rgb(200, 0, 0)
rgb(66, 66, 255)
rgb(42, 149, 248)
```

Common colors:

```css
rgb(255, 0, 0)      /* Red */
rgb(0, 255, 0)      /* Green */
rgb(0, 0, 255)      /* Blue */
rgb(255, 255, 255)  /* White */
rgb(0, 0, 0)        /* Black */
```

---

# CSS Selectors Used

## [[Class Selector]]

A class selector begins with a period (`.`).

```css
.subscribe_button{
    ...
}
```

It applies styles to every HTML element with that class.

HTML:

```html
<button class="subscribe_button">SUBSCRIBE</button>
```

---

# HTML Tags Used

## [[Style]]

The `<style>` tag contains internal CSS.

```html
<style>
    /* CSS goes here */
</style>
```

---

## [[button]]

Creates a clickable button.

```html
<button>Click Me</button>
```

Buttons can be styled with CSS and respond to user interaction.

---

# Concepts Learned

- [[HTML]]
    
- [[CSS]]
    
- [[Button Styling]]
    
- [[Class Selector]]
    
- [[Background Color]]
    
- [[Text Color]]
    
- [[Border]]
    
- [[Border Radius]]
    
- [[width]]
    
- [[height]]
    
- [[cursor]]
    
- [[Font Weight]]
    
- [[rgb()]]
    
- [[Typography]]
    

---

# Key Takeaways

- CSS classes allow reusable styles to be applied to multiple elements.
    
- `background-color` changes the button's background.
    
- `color` changes the text color.
    
- `border` can add, remove, or customize borders.
    
- `border-radius` creates rounded corners.
    
- `cursor: pointer` changes the mouse cursor to indicate a clickable element.
    
- `font-weight: bold` makes text thicker and easier to read.
    
- `rgb()` is used to define colors using red, green, and blue values.
    
- Combining these properties creates clean, modern, and professional-looking buttons.