# CSS Button Styling Notes

## Overview

This exercise demonstrates how to style buttons using CSS. Each button imitates the design of popular websites (Uber, Amazon, GitHub, Bootstrap, and LinkedIn) while introducing important CSS properties such as colors, borders, transitions, hover effects, border radius, and typography.

---

# HTML Structure

```html
<button class="uber">Request now</button>
<button class="amazon">Add to Cart</button>
<button class="github">Sign up</button>

<button class="bootstrap1">Get started</button>
<button class="bootstrap2">Download</button>

<button class="linkedin1">Apply on company website</button>
<button class="linkedin2">Save</button>
```

### Explanation

- `button` creates a clickable button.
    
- `class` assigns a CSS class to the button.
    
- The class name is used to apply specific styles.
    

Example:

```html
<button class="uber">Request now</button>
```

- `button` → HTML element
    
- `class="uber"` → Connects this button to the `.uber` CSS rule.
    
- `Request now` → Text displayed on the button.
    

---

# Complete CSS Code

```css
.uber{
    background-color: black;
    color: white;
    border: none;
    height: 50px;
    width: 145px;
    font-weight: bold;
    font-family: sans-serif;
    font-size: medium;
    transition: background-color 0.15s;
}

.uber:hover{
    background-color: rgba(0, 0, 0, 0.8);
}

.amazon{
    background-color: rgb(255, 216, 20);
    color: black;
    border: none;
    border-radius: 30px;
    width: 165px;
    height: 50px;
    font-size: medium;
    transition: background-color 0.15s;
}

.amazon:hover{
    background-color: rgb(228, 192, 8);
}

.github{
    background-color: rgb(46, 164, 79);
    color: white;
    border: none;
    border-radius: 4px;
    width: 110px;
    height: 50px;
    font-weight: bold;
    font-size: large;
    transition: box-shadow 0.15s;
}

.github:hover{
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.20);
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
    transition: background-color 0.15s;
}

.bootstrap1:hover{
    background-color: rgb(92, 41, 169);
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
    transition: background-color 0.15s,
                color 0.15s;
}

.bootstrap2:hover{
    background-color: rgb(121, 82, 179);
    color: white;
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
```

---

# CSS Properties Used

## [[background-color]]

Sets the background color of an element.

```css
background-color: black;
```

Examples:

```css
background-color: rgb(255,216,20);
background-color: rgba(0,0,0,0.8);
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

Controls the border around an element.

```css
border: none;
```

or

```css
border: 1px solid blue;
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

Larger values produce pill-shaped buttons.

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

Controls the size of the text.

```css
font-size: medium;
```

Possible values:

- small
    
- medium
    
- large
    
- xx-large
    
- 16px
    
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

---

## [[transition]]

Animates property changes smoothly.

```css
transition: background-color 0.15s;
```

Meaning:

- animate `background-color`
    
- duration is `0.15s`
    

Multiple transitions:

```css
transition:
    background-color 0.15s,
    color 0.15s;
```

---

## [[box-shadow]]

Creates a shadow around the element.

```css
box-shadow: 5px 5px 10px rgba(0,0,0,0.2);
```

Syntax:

```css
box-shadow:
horizontal
vertical
blur
color;
```

---

# CSS Functions Used

## [[rgb()]]

Creates colors using Red, Green and Blue.

```css
rgb(255,216,20)
```

Format:

```css
rgb(red, green, blue)
```

Each value ranges from **0–255**.

Examples:

```css
rgb(255,0,0)
rgb(0,255,0)
rgb(0,0,255)
```

---

## [[rgba()]]

RGBA is RGB plus Alpha (opacity).

```css
rgba(0,0,0,0.8)
```

Format:

```css
rgba(red, green, blue, alpha)
```

Alpha:

- 0 = invisible
    
- 0.5 = 50% transparent
    
- 1 = fully visible
    

Example:

```css
rgba(255,0,0,0.3)
```

---

# CSS Pseudo-Class

## [[hover]]

`:hover` applies styles when the mouse pointer is over an element.

Example:

```css
button:hover{
    background-color: red;
}
```

In this exercise:

```css
.uber:hover{
    background-color: rgba(0,0,0,0.8);
}
```

The background becomes slightly transparent while hovering.

---

# CSS Selectors Used

## [[Class Selector]]

A class selector begins with a period (`.`).

```css
.uber{
    ...
}
```

It styles every HTML element with that class.

HTML:

```html
<button class="uber">Request now</button>
```

---

## [[Pseudo-Class Selector]]

Combines a selector with a pseudo-class.

```css
.github:hover{
    box-shadow: ...
}
```

The rule only applies while the mouse is hovering.

---

# Concepts Learned

- [[CSS]]
    
- [[HTML]]
    
- [[Button Styling]]
    
- [[Class Selector]]
    
- [[Pseudo-Class]]
    
- [[Hover Effect]]
    
- [[CSS Transitions]]
    
- [[Background Color]]
    
- [[Text Color]]
    
- [[Border]]
    
- [[Border Radius]]
    
- [[Typography]]
    
- [[Box Shadow]]
    
- [[RGB Color]]
    
- [[RGBA Color]]
    
- [[CSS Functions]]
    
- [[Responsive UI Basics]]
    

---

# Key Takeaways

- CSS classes allow multiple elements to share reusable styles.
    
- `:hover` creates interactive effects.
    
- `transition` makes property changes smooth instead of instant.
    
- `rgb()` defines solid colors.
    
- `rgba()` adds transparency with an alpha channel.
    
- `border-radius` creates rounded corners.
    
- `box-shadow` adds depth and elevation to UI elements.
    
- Combining these properties produces modern, professional-looking buttons.