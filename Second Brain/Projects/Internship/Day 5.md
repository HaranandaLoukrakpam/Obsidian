# CSS Grid Layout & CSS Selectors Notes

## Overview

These exercises introduce two important CSS topics:

1. **CSS Grid** – A two-dimensional layout system used to arrange elements in rows and columns.
    
2. **CSS Selectors & Combinators** – Rules used to select specific HTML elements based on their relationships.
    

Grid is commonly used for **dashboards, galleries, cards, and full-page layouts**, while combinators allow CSS to target elements precisely.

---

# Exercise 1 — CSS Grid Layout

## Purpose

Create a layout using **CSS Grid** where certain boxes span multiple columns.

### Layout

```text
+---------+-----+-----+
|    1    |  2  |  3  |
+----+-------------+---+
| 4  |      5      |
+----+----+---------+
| 6  | 7  |    8    |
+----+----+---------+
```

---

## HTML Structure

```text
Container
│
├── Box 1
├── Box 2
├── Box 3
├── Box 4
├── Box 5
├── Box 6
├── Box 7
└── Box 8
```

---

# CSS Grid Properties

## [[display]]

Creates a Grid container.

```css
display: grid;
```

All direct children become **Grid Items**.

---

## [[CSS Grid]]

A two-dimensional layout system.

```css
display:grid;
```

Unlike Flexbox (1D), Grid manages **rows and columns simultaneously**.

---

## [[grid-template-columns]]

Defines the number and size of columns.

```css
grid-template-columns: repeat(4,100px);
```

Equivalent to

```css
grid-template-columns:
100px
100px
100px
100px;
```

---

## [[grid-template-rows]]

Defines the rows.

```css
grid-template-rows:
repeat(3,80px);
```

Creates three rows of 80px.

---

## [[repeat()]]

CSS function that repeats values.

Example

```css
repeat(4,100px)
```

Instead of writing

```css
100px 100px 100px 100px
```

---

## [[gap]]

Creates spacing between Grid items.

```css
gap:15px;
```

Works for both Grid and Flexbox.

---

## [[grid-column]]

Allows an item to span multiple columns.

Example

```css
grid-column:1 / 3;
```

Meaning

```text
Column

1     2     3     4

|-----|-----|-----|

Starts at line 1
Ends at line 3

Occupies two columns
```

Another example

```css
grid-column:2 / 5;
```

Occupies columns 2, 3 and 4.

---

# Flexbox Inside Grid

Each box also uses Flexbox.

```css
display:flex;
justify-content:center;
align-items:center;
```

Grid positions the boxes.

Flexbox centers the content inside each box.

---

# Exercise 2 — CSS Selectors

## HTML Structure

```text
Parent
│
├── Child 1
│   │
│   └── Grandchild
│
└── Child 2
```

---

# CSS Selectors

## [[Child Selector]]

Uses the `>` symbol.

```css
#parent > div
```

Selects **only direct children**.

Example

```text
Parent
├── Child ✔
├── Child ✔
└── Grandchild ✘
```

The grandchild is **not selected**.

---

## [[Descendant Selector]]

Uses a space.

```css
#parent div
```

Selects **every div inside the parent**, regardless of nesting.

Example

```text
Parent
├── Child ✔
│   └── Grandchild ✔
└── Child ✔
```

---

## [[Adjacent Sibling Selector]]

Uses the `+` operator.

```css
div + p
```

Selects the **next sibling only**.

Example

```html
<div></div>

<p>Selected</p>

<p>Not Selected</p>
```

---

## [[General Sibling Selector]]

Uses the `~` operator.

```css
div ~ p
```

Selects **all following siblings**.

Example

```html
<div></div>

<p>Selected</p>

<p>Selected</p>

<p>Selected</p>
```

---

# CSS Properties Used

## [[Border]]

Creates borders.

```css
border:3px solid black;
```

---

## [[padding]]

Creates space inside an element.

```css
padding:15px;
```

---

## [[width]]

Defines width.

Examples

```css
width:400px;
width:200px;
```

---

## [[height]]

Defines height.

Examples

```css
height:400px;
height:200px;
```

---

## [[background]]

Sets the background.

Examples

```css
background:white;
```

```css
background:#f2f2f2;
```

Unlike `background-color`, the `background` property can also accept gradients and images.

---

## [[font-size]]

Changes text size.

```css
font-size:24px;
```

---

## [[font-family]]

Changes the font.

```css
font-family:Arial,sans-serif;
```

---

## [[box-sizing]]

Determines how width and height are calculated.

```css
box-sizing:border-box;
```

---

# CSS Units

## [[Pixel (px)]]

Absolute unit.

```css
100px
```

---

## [[Pica (pc)]]

A typography unit.

Example

```css
border:10pc solid yellow;
```

### Conversion

```text
1 pc = 12 pt

1 pc ≈ 16 px
```

> **Note:** `pc` is rarely used in modern web development. `px`, `rem`, and `%` are far more common.

---

# CSS Functions

## [[repeat()]]

Repeats values in Grid definitions.

```css
repeat(4,100px)
```

---

# Grid vs Flexbox

|Feature|[[Flexbox]]|[[CSS Grid]]|
|---|---|---|
|Dimension|One|Two|
|Best For|Navigation Bars|Page Layout|
|Direction|Row OR Column|Rows AND Columns|
|Alignment|Excellent|Excellent|
|Complex Layout|Moderate|Excellent|

---

# Selector Hierarchy

```text
Parent
│
├── Child
│   └── Grandchild
│
└── Child
```

### Child Selector

```css
parent > div
```

Selects

```text
✔ Child
✔ Child
✘ Grandchild
```

---

### Descendant Selector

```css
parent div
```

Selects

```text
✔ Child
✔ Child
✔ Grandchild
```

---

# Concepts Learned

- [[CSS Grid]]
    
- [[Grid Container]]
    
- [[Grid Item]]
    
- [[display]]
    
- [[grid-template-columns]]
    
- [[grid-template-rows]]
    
- [[grid-column]]
    
- [[repeat()]]
    
- [[gap]]
    
- [[Flexbox]]
    
- [[Child Selector]]
    
- [[Descendant Selector]]
    
- [[Adjacent Sibling Selector]]
    
- [[General Sibling Selector]]
    
- [[CSS Selectors]]
    
- [[CSS Combinators]]
    
- [[Border]]
    
- [[padding]]
    
- [[width]]
    
- [[height]]
    
- [[background]]
    
- [[Font Size]]
    
- [[Font Family]]
    
- [[Box Sizing]]
    
- [[Pixel]]
    
- [[Pica]]
    

---

# Key Takeaways

- **CSS Grid** is designed for two-dimensional layouts involving both rows and columns.
    
- `display: grid` converts an element into a Grid container.
    
- `grid-template-columns` and `grid-template-rows` define the grid's structure.
    
- `repeat()` simplifies repetitive Grid definitions.
    
- `grid-column` allows elements to span multiple columns.
    
- Grid and Flexbox complement each other—Grid controls the overall layout, while Flexbox is often used to align content within Grid items.
    
- CSS **combinators** select elements based on their relationships:
    
    - `>` selects direct children.
        
    - A space selects all descendants.
        
    - `+` selects the next adjacent sibling.
        
    - `~` selects all following siblings.
        
- The `background` property is more versatile than `background-color`, supporting colors, images, and gradients.
    
- Although `pc` (pica) is a valid CSS unit, modern web development primarily uses `px`, `%`, `em`, and `rem`.