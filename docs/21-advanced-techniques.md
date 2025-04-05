# Advanced CSS Techniques

This guide covers advanced CSS techniques and features that can help you create more sophisticated and performant web designs.

## CSS Custom Properties (Variables)

CSS Custom Properties allow you to store and reuse values throughout your stylesheet.

```css
:root {
  --primary-color: #3498db;
  --secondary-color: #2ecc71;
  --spacing-unit: 1rem;
  --border-radius: 8px;
}

.button {
  background-color: var(--primary-color);
  padding: var(--spacing-unit);
  border-radius: var(--border-radius);
}

/* Dynamic values with calc() */
.container {
  width: calc(100% - var(--spacing-unit) * 2);
  margin: 0 var(--spacing-unit);
}

/* Fallback values */
.element {
  color: var(--custom-color, #000);
}
```

## CSS Grid Advanced Features

### 1. Grid Template Areas

```css
.grid-container {
  display: grid;
  grid-template-areas:
    "header header header"
    "nav main sidebar"
    "footer footer footer";
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto 1fr auto;
}

.header {
  grid-area: header;
}
.nav {
  grid-area: nav;
}
.main {
  grid-area: main;
}
.sidebar {
  grid-area: sidebar;
}
.footer {
  grid-area: footer;
}
```

### 2. Auto-Fit and Auto-Fill

```css
/* Auto-fit: collapses empty tracks */
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}

/* Auto-fill: keeps empty tracks */
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1rem;
}
```

### 3. Grid Line Names

```css
.grid-container {
  display: grid;
  grid-template-columns: [sidebar-start] 200px [sidebar-end main-start] 1fr [main-end];
  grid-template-rows: [header-start] auto [header-end content-start] 1fr [content-end footer-start] auto [footer-end];
}

.sidebar {
  grid-column: sidebar-start / sidebar-end;
  grid-row: header-end / footer-start;
}
```

## Advanced Flexbox Techniques

### 1. Flexbox Order

```css
.flex-container {
  display: flex;
}

.item-1 {
  order: 3;
}
.item-2 {
  order: 1;
}
.item-3 {
  order: 2;
}
```

### 2. Flex Grow and Shrink

```css
.flex-container {
  display: flex;
}

.item-1 {
  flex-grow: 2;
} /* Takes up twice the space */
.item-2 {
  flex-grow: 1;
} /* Takes up normal space */
.item-3 {
  flex-shrink: 0;
} /* Won't shrink */
```

### 3. Flex Basis

```css
.flex-container {
  display: flex;
}

.item {
  flex: 1 1 200px; /* grow | shrink | basis */
}
```

## Advanced Selectors

### 1. Attribute Selectors

```css
/* Exact match */
[type="text"] {
}

/* Contains */
[class*="btn"] {
}

/* Starts with */
[class^="btn-"] {
}

/* Ends with */
[class$="-primary"] {
}

/* Contains word */
[class~="active"] {
}
```

### 2. Pseudo-Classes

```css
/* First and last children */
li:first-child {
}
li:last-child {
}

/* Nth child */
li:nth-child(2n) {
} /* Even items */
li:nth-child(2n + 1) {
} /* Odd items */
li:nth-child(3) {
} /* Third item */

/* Type selectors */
p:first-of-type {
}
p:last-of-type {
}

/* Empty elements */
div:empty {
}

/* Not selector */
div:not(.special) {
}
```

### 3. Pseudo-Elements

```css
/* Content */
.element::before {
  content: "→";
}

/* First letter and line */
p::first-letter {
  font-size: 2em;
}

p::first-line {
  font-weight: bold;
}

/* Selection */
::selection {
  background: yellow;
  color: black;
}
```

## Advanced Animations

### 1. Keyframe Animations

```css
@keyframes slide-in {
  0% {
    transform: translateX(-100%);
    opacity: 0;
  }
  50% {
    transform: translateX(0);
    opacity: 0.5;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

.element {
  animation: slide-in 1s ease-out forwards;
}
```

### 2. Animation Properties

```css
.element {
  animation-name: slide-in;
  animation-duration: 1s;
  animation-timing-function: ease-out;
  animation-delay: 0.5s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-fill-mode: forwards;
  animation-play-state: running;
}
```

### 3. Multiple Animations

```css
@keyframes fade {
  to {
    opacity: 0;
  }
}

@keyframes slide {
  to {
    transform: translateX(100%);
  }
}

.element {
  animation: fade 1s ease-out forwards, slide 1s ease-out forwards;
}
```

## Advanced Transforms

### 1. 3D Transforms

```css
.card {
  transform-style: preserve-3d;
  perspective: 1000px;
}

.card-face {
  backface-visibility: hidden;
}

.card-back {
  transform: rotateY(180deg);
}

.card:hover {
  transform: rotateY(180deg);
}
```

### 2. Transform Origin

```css
.element {
  transform-origin: top left;
  transform: rotate(45deg);
}

.element {
  transform-origin: 50% 50%;
  transform: scale(1.5);
}
```

## Advanced Layout Techniques

### 1. CSS Columns

```css
.text-content {
  column-count: 3;
  column-gap: 2rem;
  column-rule: 1px solid #ccc;
}

/* Column breaks */
.heading {
  column-span: all;
}

.break-before {
  break-before: column;
}
```

### 2. CSS Shapes

```css
.text-wrap {
  shape-outside: circle(50%);
  float: left;
  width: 300px;
  height: 300px;
}

.text-wrap {
  shape-outside: polygon(0 0, 100% 0, 100% 100%, 0 100%);
}
```

### 3. CSS Grid Auto-Placement

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  grid-auto-rows: 100px;
  grid-auto-flow: dense;
}
```

## Advanced Filter Effects

### 1. Multiple Filters

```css
.image {
  filter: brightness(1.2) contrast(1.1) saturate(1.3) grayscale(0.5);
}
```

### 2. Filter Combinations

```css
.image {
  filter: url('#custom-filter');
}

/* SVG Filter */
<svg>
  <defs>
    <filter id="custom-filter">
      <feGaussianBlur in="SourceGraphic" stdDeviation="5" />
      <feColorMatrix type="matrix" values="
        1 0 0 0 0
        0 1 0 0 0
        0 0 1 0 0
        0 0 0 1 0
      "/>
    </filter>
  </defs>
</svg>
```

## Performance Optimization

### 1. Will-Change

```css
.element {
  will-change: transform, opacity;
}

/* Use sparingly and remove when not needed */
.element.animated {
  will-change: transform;
}
```

### 2. Contain Property

```css
.element {
  contain: content; /* Size and position are independent */
}

.element {
  contain: layout style paint; /* Optimize rendering */
}
```

### 3. Content Visibility

```css
.element {
  content-visibility: auto;
  contain-intrinsic-size: 0 500px; /* Estimated size */
}
```

## Best Practices

1. Use CSS Custom Properties for theming and maintainable code
2. Implement responsive layouts using Grid and Flexbox
3. Optimize animations using transform and opacity
4. Use advanced selectors judiciously
5. Consider performance implications of advanced features
6. Test across different browsers and devices
7. Use CSS containment for better performance
8. Implement progressive enhancement
9. Keep accessibility in mind
10. Document complex CSS patterns

## Next Steps

- Explore [CSS-in-JS Solutions](22-css-in-js.md)
