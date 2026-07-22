# Day 7 – CSS Animations, Media Queries, Responsive Grid, Audio & Video

## Overview

This exercise introduces **CSS animations**, **transitions**, **responsive design using media queries**, **CSS Grid**, and **HTML multimedia elements**. It also demonstrates how animations are created using `@keyframes`, how layouts adapt to different screen sizes, and how media like audio and video are embedded into webpages.

---

# Concepts Covered

## 1. CSS Transition

A **transition** creates a smooth change between two states of an element.

### Syntax

```css
transition: property duration timing-function;
```

Example:

```css
.parent{
    transition: transform 1s ease-in-out;
}

.parent:hover{
    transform: translateX(100px);
}
```

Here:

- `transform` → property to animate
- `1s` → duration
- `ease-in-out` → speed curve

---

## 2. CSS Transform

The `transform` property changes an element's position, size, or rotation.

Functions used:

- `translateX()`
- `translateY()`
- `translate()`
- `scale()`
- `rotate()`

Example

```css
transform: translateX(100px);
```

Moves element 100px to the right.

---

## 3. CSS Animation

Animations automatically change CSS properties over time.

Syntax

```css
animation:
    animation-name
    animation-duration
    animation-iteration-count;
```

Example

```css
animation: slide 3s infinite alternate;
```

Meaning:

- animation name → `slide`
- duration → `3 seconds`
- repeats forever
- alternate direction every cycle

---

## 4. @keyframes

`@keyframes` defines each stage of an animation.

Example

```css
@keyframes slide{
    0%{
        transform: translateX(0);
    }

    50%{
        transform: translateY(100px);
    }

    100%{
        transform: translateY(200px);
    }
}
```

Animation stages:

- 0% → starting position
- 50% → halfway
- 100% → final position

---

## 5. Scale Animation

Changes an element's size.

```css
transform: scale(4);
```

Means the object becomes **4 times larger**.

---

## 6. Rotate

Rotates an element.

```css
transform: rotate(360deg);
```

One complete rotation.

---

## 7. Transform Origin

Defines the pivot point for rotations.

Example

```css
transform-origin: bottom right;
```

Instead of rotating around the center, it rotates around the bottom-right corner.

---

## 8. Text Animation

Animation applied to headings and paragraphs.

```css
@keyframes text-animation{
    0%{
        opacity:0;
        transform:translateY(-20px);
    }

    100%{
        opacity:1;
        transform:translateY(0);
    }
}
```

Effects:

- fades in
- slides downward
- appears smoothly

---

## 9. CSS Grid

Creates a two-dimensional layout.

Container

```css
display:grid;
```

Columns

```css
grid-template-columns: repeat(5,1fr);
```

Creates **5 equal columns**.

---

## 10. Media Queries

Media queries make websites responsive.

Syntax

```css
@media screen and (max-width:1200px){
}
```

Meaning:

Apply these styles only when screen width is **1200px or smaller**.

---

### Responsive Breakpoints

#### Desktop

```css
repeat(5,1fr)
```

5 columns

---

#### Tablet

```css
repeat(3,1fr)
```

3 columns

---

#### Small Tablet

```css
repeat(2,1fr)
```

2 columns

---

#### Mobile

```css
repeat(1,1fr)
```

1 column

Button color changes

```css
background-color:yellow;
color:black;
```

Paragraph text becomes green.

---

## 11. HTML Video

```html
<video controls autoplay>
```

Attributes

- `controls`
- `autoplay`

---

## 12. HTML Audio

```html
<audio controls>
```

Uses multiple `<source>` elements.

Benefits:

- Browser compatibility
- Multiple file formats

---

## 13. HTML Source Element

```html
<source src="viper.mp3" type="audio/mp3">
```

Provides media files for browsers.

---

## 14. CSS Properties Used

### Layout

- `display`
- `grid`
- `grid-template-columns`
- `gap`
- `margin`
- `width`
- `height`

### Animation

- `transition`
- `transform`
- `translateX()`
- `translateY()`
- `translate()`
- `rotate()`
- `scale()`
- `animation`
- `animation-duration`
- `animation-name`
- `animation-fill-mode`
- `animation-timing-function`
- `animation-iteration-count`
- `animation-direction`
- `transform-origin`
- `@keyframes`

### Styling

- `background-color`
- `border`
- `color`
- `padding`
- `cursor`
- `border-radius`

### Responsive

- `@media`
- `max-width`

### Typography

- `opacity`

---

# HTML Elements Used

- `<video>`
- `<audio>`
- `<source>`
- `<button>`
- `<div>`
- `<p>`
- `<h1>`
- `<span>`

---

# Key Takeaways

- Transitions animate one property change.
- Animations use `@keyframes` for multiple stages.
- `transform` moves, rotates, and scales elements.
- CSS Grid creates responsive layouts.
- Media Queries adapt layouts to different screen sizes.
- HTML supports multimedia through `<video>` and `<audio>`.

---

# Source Code

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Day-7</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>

    <div id="parent5">
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>

        <button>Click me</button>
    </div>

    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>

</body>
</html>
```

```css
.parent{
    transition: transform 1s ease-in-out;
}

.parent:hover{
    transform: translateX(100px);
}

@keyframes slide{
    0%{transform:translateX(0);}
    50%{transform:translateY(100px);}
    80%{transform:translateX(150px);}
    100%{transform:translateY(200px);}
}

.parent1{
    animation:slide 3s infinite alternate;
}

@keyframes scale{
    0%,100%{
        transform:scale(1);
    }
    50%{
        transform:scale(4);
    }
}

.parent2{
    animation:scale 2s infinite alternate;
}

.parent3{
    transform-origin:bottom right;
    transition:transform 4s ease-in-out;
}

.parent3:hover{
    transform:rotate(360deg);
}

.parent4{
    transition:transform 2s ease-in-out;
}

.parent4:hover{
    transform:translate(500px,500px);
}

@keyframes text-animation{
    0%{
        opacity:0;
        transform:translateY(-20px);
    }

    100%{
        opacity:1;
        transform:translateY(0);
    }
}

h1,h2,h3,h4,h5,h6,p,span{
    animation:text-animation 2s ease-in-out both;
}

#parent5{
    width:80%;
    margin:auto;
    display:grid;
    grid-template-columns:repeat(5,1fr);
    gap:20px;
}

#parent5>div{
    width:200px;
    height:200px;
    background:yellowgreen;
}

button{
    padding:10px 20px;
    background:teal;
    color:white;
}

p{
    color:red;
}

@media screen and (max-width:1200px){
    #parent5{
        grid-template-columns:repeat(3,1fr);
    }
}

@media screen and (max-width:850px){
    #parent5{
        grid-template-columns:repeat(2,1fr);
    }
}

@media screen and (max-width:550px){
    #parent5{
        grid-template-columns:repeat(1,1fr);
    }

    button{
        background:yellow;
        color:black;
    }

    p{
        color:green;
    }
}
```

---

# Tags

- [[HTML]]
- [[CSS]]
- [[CSS Transition]]
- [[CSS Animation]]
- [[Transform]]
- [[Translate]]
- [[TranslateX]]
- [[TranslateY]]
- [[Rotate]]
- [[Scale]]
- [[Transform Origin]]
- [[Keyframes]]
- [[Animation]]
- [[Transition]]
- [[Media Queries]]
- [[Responsive Design]]
- [[CSS Grid]]
- [[Grid Layout]]
- [[Display Grid]]
- [[Grid Template Columns]]
- [[Repeat Function]]
- [[Fraction Unit (fr)]]
- [[Opacity]]
- [[Button]]
- [[Video]]
- [[Audio]]
- [[Source Element]]
- [[HTML Multimedia]]
- [[Viewport]]
- [[Responsive Web Design]]
- [[CSS]]
- [[Day 7]]