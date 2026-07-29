# Responsive Landing Page Notes (HTML + CSS)

## Overview

This project combines many HTML and CSS concepts learned so far into a **modern landing page**. It includes:

- Navigation Bar
    
- Hero (Banner) Section
    
- CSS Grid Gallery
    
- Pricing Cards
    
- Hover Animations
    
- External CSS
    
- Flexbox
    
- CSS Grid
    
- Transitions
    
- Gradients
    
- Shadows
    

It demonstrates how multiple layout techniques work together to create a professional-looking website.

---

# Website Structure

```text
Website
│
├── Navigation Bar
│   ├── Logo
│   └── Menu
│
├── Hero Banner
│   ├── Text
│   └── Image
│
├── Image Gallery (Grid)
│
└── Pricing Section
    ├── Basic
    ├── Standard
    └── Premium
```

---

# HTML Elements Used

## [[nav]]

Represents the navigation area.

```html
<nav>
</nav>
```

Contains the logo and navigation menu.

---

## [[section]]

Groups related content together.

Examples

```html
<section id="banner">
```

```html
<section id="grid">
```

```html
<section id="price">
```

Each section represents one part of the webpage.

---

## [[div]]

Generic container.

Used for

- Logo
    
- Menu
    
- Cards
    
- Banner content
    
- Gallery items
    

---

## [[h1]]

Main heading.

```html
<h1>Welcome to Our Awesome Website</h1>
```

---

## [[h2]]

Subheadings.

Used for

- Logo
    
- Pricing titles
    

---

## [[h3]]

Displays the product prices.

```html
<h3>$20</h3>
```

---

## [[p]]

Paragraph text.

Used for

- Navigation labels
    
- Descriptions
    
- Pricing details
    

---

## [[span]]

Inline container.

```html
<h1>
Welcome to Our
<span>Awesome</span>
Website
</h1>
```

Allows only one word to receive different styling.

---

## [[img]]

Displays images.

```html
<img src="image.jpg">
```

---

## [[button]]

Clickable button.

```html
<button>
Buy Now
</button>
```

---

## [[a]]

Hyperlink.

```html
<a href="about.html">
About
</a>
```

Navigates between pages.

---

## [[link]]

Loads an external stylesheet.

```html
<link
rel="stylesheet"
href="style.css">
```

---

# CSS Selectors Used

## [[Universal Selector]]

```css
*{
margin:0;
padding:0;
box-sizing:border-box;
}
```

Resets default browser styling.

---

## [[ID Selector]]

Uses `#`

Example

```css
#banner{
}
```

Targets one unique element.

---

## [[Element Selector]]

Targets HTML elements directly.

Example

```css
nav{
}
```

```css
button{
}
```

---

## [[Child Selector]]

Uses `>`.

```css
#banner > div{
}
```

Selects only direct children.

---

## [[Hover Selector]]

```css
button:hover{
}
```

Applies styles when the mouse hovers.

---

# CSS Layout Techniques

# [[Flexbox]]

Used in multiple sections.

Example

```css
display:flex;
```

---

## [[justify-content]]

Aligns items horizontally.

```css
justify-content:space-between;
```

Other values

- center
    
- flex-start
    
- flex-end
    
- space-around
    
- space-evenly
    

---

## [[align-items]]

Aligns items vertically.

```css
align-items:center;
```

---

## [[gap]]

Creates spacing.

```css
gap:40px;
```

---

# [[CSS Grid]]

Used in the gallery.

```css
display:grid;
```

---

## [[grid-template-columns]]

Creates four equal columns.

```css
grid-template-columns:
repeat(4,1fr);
```

---

## [[repeat()]]

Repeats values.

```css
repeat(4,1fr)
```

Equivalent to

```css
1fr 1fr 1fr 1fr
```

---

## [[Fraction Unit (fr)]]

Represents a fraction of available space.

```css
1fr
```

If there are four columns

```text
1fr 1fr 1fr 1fr
```

Each receives equal width.

---

# CSS Properties Used

## [[width]]

Sets width.

Examples

```css
width:90%;
```

```css
width:50%;
```

---

## [[height]]

Sets height.

```css
height:80px;
```

---

## [[margin]]

Creates space outside elements.

Examples

```css
margin:auto;
```

```css
margin:80px auto;
```

---

## [[padding]]

Creates space inside elements.

```css
padding:40px 30px;
```

---

## [[background]]

Sets backgrounds.

Examples

```css
background:white;
```

```css
background:teal;
```

---

## [[linear-gradient()]]

Creates smooth color transitions.

```css
background:
linear-gradient(
135deg,
#008080,
#0f766e
);
```

---

## [[color]]

Changes text color.

```css
color:white;
```

---

## [[font-size]]

Controls text size.

Examples

```css
font-size:55px;
```

```css
font-size:16px;
```

---

## [[font-weight]]

Changes text thickness.

```css
font-weight:500;
```

---

## [[line-height]]

Controls spacing between lines.

```css
line-height:1.8;
```

Improves readability.

---

## [[letter-spacing]]

Controls spacing between letters.

```css
letter-spacing:2px;
```

---

## [[text-align]]

Aligns text.

```css
text-align:center;
```

---

## [[text-decoration]]

Removes underline.

```css
text-decoration:none;
```

Common for navigation links.

---

## [[Border]]

Creates borders.

```css
border:none;
```

---

## [[border-radius]]

Rounds corners.

Examples

```css
border-radius:8px;
```

```css
border-radius:20px;
```

---

## [[box-shadow]]

Creates shadows.

Example

```css
box-shadow:
0 10px 30px rgba(0,0,0,.1);
```

Used for

- Cards
    
- Images
    
- Navigation
    

---

## [[object-fit]]

Controls image resizing.

```css
object-fit:contain;
```

Ensures images fit without distortion.

Common values

- contain
    
- cover
    
- fill
    

---

## [[cursor]]

Changes mouse cursor.

```css
cursor:pointer;
```

---

# CSS Animation Properties

## [[transition]]

Animates property changes smoothly.

Example

```css
transition:.4s;
```

---

## [[transform]]

Transforms elements.

### Scale

```css
transform:scale(1.05);
```

Enlarges the image slightly.

---

### Translate

```css
transform:translateY(-10px);
```

Moves the element upward.

---

# CSS Functions

## [[rgba()]]

Creates colors with transparency.

Example

```css
rgba(0,0,0,.15)
```

Used inside shadows.

---

## [[linear-gradient()]]

Creates gradient backgrounds.

---

## [[repeat()]]

Repeats Grid values.

---

# CSS Units

## [[Pixel (px)]]

Absolute measurement.

```css
40px
```

---

## [[Percentage (%) ]]

Relative to parent element.

```css
width:90%;
```

---

## [[Fraction (fr)]]

Grid unit.

```css
1fr
```

Shares available space equally.

---

# Project Layout

```text
Navigation
│
├── Logo
└── Menu

↓

Banner
├── Text
└── Image

↓

Grid Gallery
□ □ □ □
□ □ □ □

↓

Pricing
┌─────┐
│Basic│
├─────┤
│$10  │
└─────┘

┌────────┐
│Standard│
├────────┤
│$20     │
└────────┘

┌────────┐
│Premium │
├────────┤
│$30     │
└────────┘
```

---

# Concepts Learned

- [[HTML]]
    
- [[CSS]]
    
- [[Landing Page]]
    
- [[Navigation Bar]]
    
- [[Hero Section]]
    
- [[Image Gallery]]
    
- [[Pricing Card]]
    
- [[Flexbox]]
    
- [[CSS Grid]]
    
- [[Grid Container]]
    
- [[Grid Item]]
    
- [[section]]
    
- [[div]]
    
- [[span]]
    
- [[Anchor]]
    
- [[button]]
    
- [[Image]]
    
- [[Universal Selector]]
    
- [[ID Selector]]
    
- [[Child Selector]]
    
- [[Hover Selector]]
    
- [[display]]
    
- [[Justify Content]]
    
- [[Align Items]]
    
- [[gap]]
    
- [[width]]
    
- [[height]]
    
- [[margin]]
    
- [[padding]]
    
- [[background]]
    
- [[Linear Gradient]]
    
- [[color]]
    
- [[Font Size]]
    
- [[Font Weight]]
    
- [[Line Height]]
    
- [[Letter Spacing]]
    
- [[Text Align]]
    
- [[Text Decoration]]
    
- [[Border Radius]]
    
- [[Box Shadow]]
    
- [[Object Fit]]
    
- [[transition]]
    
- [[transform]]
    
- [[Scale]]
    
- [[Translate]]
    
- [[cursor]]
    
- [[RGBA]]
    
- [[Repeat]]
    
- [[Fraction Unit (fr)]]
    
- [[Percentage]]
    
- [[Pixel]]
    

---

# Key Takeaways

- A **landing page** combines multiple HTML sections into one cohesive webpage.
    
- **Flexbox** is ideal for one-dimensional layouts such as navigation bars, banners, and pricing cards.
    
- **CSS Grid** is well suited for image galleries and other two-dimensional layouts.
    
- The `fr` unit automatically distributes available space evenly across grid columns.
    
- `transition` and `transform` create smooth, interactive hover animations without JavaScript.
    
- `linear-gradient()` enhances backgrounds with smooth color transitions.
    
- `box-shadow` adds visual depth and makes cards and images stand out.
    
- `object-fit: contain` ensures images scale correctly while preserving their aspect ratio.
    
- Separating HTML structure from CSS presentation using an external stylesheet improves maintainability and follows modern web development best practices.