# CSS Flexbox Layout Notes (Cards & Keyboard)

## Overview

These two exercises demonstrate the power of **CSS Flexbox** for building modern layouts.

- **Exercise 1:** Creates a responsive card grid using Flexbox.
    
- **Exercise 2:** Builds a realistic computer keyboard using nested Flexbox containers.
    

These exercises also introduce several new CSS concepts such as **ID selectors**, **universal selectors**, **Flexbox direction**, **wrapping**, **spacing**, **gradients**, **box-sizing**, **user-select**, and **multiple box shadows**.

---

# Exercise 1 — Flexbox Card Layout

## Purpose

Build a responsive container that automatically arranges cards into rows.

### Structure

```text
Container (#container)
│
├── Apple
├── Banana
├── Cucumber
├── Daikon
├── Fruits
├── Elephant
├── Grape
└── Indigo
```

---

## New HTML Concepts

### [[id]]

Assigns a unique identifier to an element.

```html
<div id="container">
```

Unlike a class, an ID should only be used **once** on a webpage.

CSS selector

```css
#container{
}
```

---

### [[class]]

Assigns reusable styles.

```html
<div class="child">
```

CSS

```css
.child{
}
```

---

# Exercise 2 — Keyboard Layout

## Purpose

Create an entire keyboard using nested Flexbox containers.

### Structure

```text
keyboard-container
│
├── Heading
├── Row 1
├── Row 2
├── Row 3
├── Row 4
├── Row 5
└── Row 6
```

Each row is another Flexbox container.

---

# CSS Selectors

## [[Universal Selector]]

Selects every element.

```css
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}
```

Commonly used as a CSS reset.

---

## [[ID Selector]]

Uses the `#` symbol.

```css
#container{
}
```

Targets exactly one element.

---

## [[Class Selector]]

Uses the `.` symbol.

```css
.child{
}
```

Can be reused many times.

---

# CSS Properties Used

## [[display]]

Changes how an element is displayed.

```css
display:flex;
```

Creates a Flexbox container.

---

## [[Flexbox]]

Modern CSS layout system.

```css
display:flex;
```

Makes arranging elements much easier than older techniques.

---

## [[flex-direction]]

Determines the main axis.

```css
flex-direction:column;
```

Values

- row
    
- row-reverse
    
- column
    
- column-reverse
    

Example

```text
row

□ □ □ □
```

```text
column

□
□
□
□
```

---

## [[flex-wrap]]

Controls whether items wrap onto another line.

```css
flex-wrap:wrap;
```

Without wrapping

```text
□□□□□□□□□□□□
```

With wrapping

```text
□□□□
□□□□
□□□□
```

---

## [[justify-content]]

Aligns items along the main axis.

```css
justify-content:center;
```

Examples

- flex-start
    
- center
    
- flex-end
    
- space-between
    
- space-around
    
- space-evenly
    

---

## [[align-items]]

Aligns items along the cross axis.

```css
align-items:center;
```

---

## [[gap]]

Creates spacing between Flexbox items.

```css
gap:8px;
```

Instead of margins between every item, `gap` handles spacing automatically.

---

## [[width]]

Defines width.

Examples

```css
width:50%;
```

```css
width:150px;
```

---

## [[height]]

Defines height.

```css
height:150px;
```

---

## [[margin]]

Creates space outside an element.

Examples

```css
margin:auto;
margin-top:50px;
margin:10px;
```

---

## [[padding]]

Creates space inside an element.

```css
padding:10px;
```

---

## [[border]]

Creates borders.

```css
border:1px solid gray;
```

---

## [[border-radius]]

Rounds element corners.

Examples

```css
border-radius:5px;
border-radius:30px;
```

---

## [[background-color]]

Changes background color.

Examples

```css
background-color:#1F3A5F;
```

```css
background-color:antiquewhite;
```

---

## [[color]]

Changes text color.

```css
color:#1F3A5F;
```

---

## [[font-family]]

Changes the font.

Examples

```css
font-family:serif;
```

```css
font-family:-apple-system, BlinkMacSystemFont, sans-serif;
```

---

## [[font-size]]

Changes text size.

```css
font-size:40px;
```

---

## [[font-weight]]

Changes text thickness.

Examples

```css
font-weight:500;
```

```css
font-weight:600;
```

---

## [[letter-spacing]]

Controls spacing between letters.

```css
letter-spacing:8px;
```

---

## [[cursor]]

Changes the mouse cursor.

```css
cursor:default;
```

Common values

- pointer
    
- default
    
- text
    
- move
    

---

## [[box-shadow]]

Adds shadows.

Example

```css
box-shadow:
0 2px 6px rgba(0,0,0,.08),
0 8px 20px rgba(0,0,0,.04);
```

Syntax

```css
horizontal
vertical
blur
color
```

Multiple shadows can be applied simultaneously.

---

## [[box-sizing]]

Controls how width and height are calculated.

```css
box-sizing:border-box;
```

With `border-box`, padding and borders are included inside the specified width.

---

## [[user-select]]

Determines whether text can be selected.

```css
user-select:none;
```

Useful for buttons and keyboard keys.

---

# CSS Functions

## [[linear-gradient()]]

Creates a smooth color gradient.

```css
background:
linear-gradient(
135deg,
#F5F5F7,
#ECECEF,
#E8E8ED
);
```

Instead of one solid color, multiple colors blend together.

---

## [[rgba()]]

Creates colors with transparency.

```css
rgba(0,0,0,.08)
```

The last value represents opacity.

```
0   → Invisible
0.5 → 50%
1   → Fully visible
```

---

# CSS Units

## [[px]]

Absolute pixel unit.

Example

```css
width:150px;
```

---

## [[Percentage]]

Relative size.

```css
width:50%;
```

50% of the parent element.

---

## [[Viewport Height (vh)]]

Represents a percentage of the browser height.

```css
height:100vh;
```

100vh means the entire visible browser height.

---

# Flexbox Hierarchy

```text
Keyboard Container
│
├── Row
│   ├── Key
│   ├── Key
│   ├── Key
│   └── ...
│
├── Row
│   ├── Key
│   └── ...
│
└── More Rows
```

Each row is itself a Flexbox container.

---

# Concepts Learned

- [[HTML]]
    
- [[CSS]]
    
- [[Flexbox]]
    
- [[Flex Container]]
    
- [[Flex Item]]
    
- [[display]]
    
- [[flex-direction]]
    
- [[flex-wrap]]
    
- [[justify-content]]
    
- [[align-items]]
    
- [[gap]]
    
- [[Universal Selector]]
    
- [[ID Selector]]
    
- [[Class Selector]]
    
- [[margin]]
    
- [[padding]]
    
- [[Border]]
    
- [[Border Radius]]
    
- [[Background Color]]
    
- [[Color]]
    
- [[Font Family]]
    
- [[Font Size]]
    
- [[Font Weight]]
    
- [[Letter Spacing]]
    
- [[Cursor]]
    
- [[Box Shadow]]
    
- [[Box Sizing]]
    
- [[User Select]]
    
- [[Linear Gradient]]
    
- [[RGBA]]
    
- [[Viewport Height]]
    
- [[Pixel]]
    
- [[Percentage]]
    

---

# Key Takeaways

- Flexbox is the preferred modern layout system for arranging elements.
    
- A Flexbox layout can contain other Flexbox layouts (nested Flexbox), as shown in the keyboard example.
    
- `flex-wrap` allows items to move to a new row automatically when there isn't enough space.
    
- `gap` provides clean spacing between Flexbox items without needing margins on every element.
    
- `box-sizing: border-box` simplifies layout calculations by including padding and borders within the element's width and height.
    
- `box-shadow` can create depth using one or multiple shadows.
    
- `linear-gradient()` creates smooth background transitions between colors.
    
- `user-select: none` prevents users from selecting text, making interfaces like keyboards feel more natural.
    
- Combining Flexbox, spacing, shadows, and rounded corners allows you to build modern, responsive UI components with relatively little CSS.