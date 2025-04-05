# Performance Optimization

Optimizing CSS performance is crucial for creating fast-loading, responsive websites. This guide covers techniques to improve CSS rendering speed and reduce resource usage.

## CSS Loading Optimization

### 1. Critical CSS

```html
<!-- Inline critical CSS in the head -->
<style>
  /* Critical styles for above-the-fold content */
  body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
  }
  .header {
    background: #333;
    color: white;
    padding: 1rem;
  }
</style>

<!-- Defer non-critical CSS -->
<link
  rel="preload"
  href="styles.css"
  as="style"
  onload="this.onload=null;this.rel='stylesheet'"
/>
<noscript><link rel="stylesheet" href="styles.css" /></noscript>
```

### 2. CSS Splitting

```html
<!-- Load only the CSS needed for the current page -->
<link rel="stylesheet" href="common.css" />
<link rel="stylesheet" href="home.css" />
```

### 3. Media Queries for Loading

```html
<!-- Load print styles only when printing -->
<link rel="stylesheet" href="print.css" media="print" />

<!-- Load mobile styles first, then desktop styles -->
<link rel="stylesheet" href="mobile.css" />
<link rel="stylesheet" href="desktop.css" media="(min-width: 768px)" />
```

## Selector Optimization

### 1. Avoid Universal Selectors

```css
/* Avoid */
* {
  margin: 0;
  padding: 0;
}

/* Better */
html,
body,
div,
p,
h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
  padding: 0;
}
```

### 2. Minimize Specificity

```css
/* Avoid */
div.container > ul > li > a {
  color: blue;
}

/* Better */
.nav-link {
  color: blue;
}
```

### 3. Avoid Descendant Selectors

```css
/* Avoid */
div p span {
  color: red;
}

/* Better */
.highlight {
  color: red;
}
```

### 4. Use Shorthand Properties

```css
/* Avoid */
.element {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 10px;
  margin-left: 20px;
}

/* Better */
.element {
  margin: 10px 20px;
}
```

## Rendering Performance

### 1. Avoid Layout Thrashing

```css
/* Avoid properties that trigger layout recalculation */
.element {
  width: 100px;
  height: 100px;
  position: absolute;
  top: 0;
  left: 0;
}

/* Use transform instead when possible */
.element {
  width: 100px;
  height: 100px;
  transform: translate(0, 0);
}
```

### 2. Use GPU Acceleration

```css
/* Properties that trigger GPU acceleration */
.element {
  transform: translateZ(0);
  /* or */
  transform: translate3d(0, 0, 0);
  /* or */
  will-change: transform;
}
```

### 3. Reduce Repaints

```css
/* Avoid properties that trigger repaints */
.element {
  color: red;
  background-color: blue;
  border: 1px solid black;
}

/* Use opacity or transform when possible */
.element {
  opacity: 0.8;
  transform: scale(1.1);
}
```

## Animation Performance

### 1. Use Transform and Opacity

```css
/* Avoid animating layout properties */
.element {
  animation: bad-animation 1s infinite;
}

@keyframes bad-animation {
  0% {
    width: 100px;
  }
  50% {
    width: 200px;
  }
  100% {
    width: 100px;
  }
}

/* Better: use transform */
.element {
  animation: good-animation 1s infinite;
}

@keyframes good-animation {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(2);
  }
  100% {
    transform: scale(1);
  }
}
```

### 2. Use will-change

```css
/* Hint to browser about upcoming animations */
.element {
  will-change: transform, opacity;
  transition: transform 0.3s, opacity 0.3s;
}

.element:hover {
  transform: scale(1.1);
  opacity: 0.8;
}
```

### 3. Limit Animation Duration

```css
/* Keep animations short */
.element {
  transition: all 0.3s ease;
}

/* Avoid long animations */
.element {
  transition: all 2s ease;
}
```

## CSS File Size Optimization

### 1. Minification

```css
/* Before minification */
.element {
  background-color: #ffffff;
  margin: 10px 20px 10px 20px;
  padding: 5px 10px 5px 10px;
}

/* After minification */
.element {
  background-color: #fff;
  margin: 10px 20px;
  padding: 5px 10px;
}
```

### 2. Remove Unused CSS

```css
/* Remove unused selectors */
.unused-class {
  color: red;
}

/* Keep only what's needed */
.used-class {
  color: blue;
}
```

### 3. Consolidate Similar Rules

```css
/* Before consolidation */
.button-primary {
  background: blue;
  color: white;
  padding: 10px;
}

.button-secondary {
  background: green;
  color: white;
  padding: 10px;
}

/* After consolidation */
.button-primary,
.button-secondary {
  color: white;
  padding: 10px;
}

.button-primary {
  background: blue;
}

.button-secondary {
  background: green;
}
```

## Responsive Images

### 1. Use srcset and sizes

```html
<img
  src="small.jpg"
  srcset="small.jpg 300w, medium.jpg 600w, large.jpg 900w"
  sizes="(max-width: 600px) 300px,
            (max-width: 900px) 600px,
            900px"
  alt="Responsive image"
/>
```

### 2. Use picture Element

```html
<picture>
  <source media="(min-width: 800px)" srcset="large.jpg" />
  <source media="(min-width: 400px)" srcset="medium.jpg" />
  <img src="small.jpg" alt="Responsive image" />
</picture>
```

## CSS Variables Performance

### 1. Limit Variable Usage

```css
/* Avoid excessive variable usage */
.element {
  --var1: value1;
  --var2: value2;
  --var3: value3;
  --var4: value4;
  --var5: value5;
  --var6: value6;
  --var7: value7;
  --var8: value8;
  --var9: value9;
  --var10: value10;

  property1: var(--var1);
  property2: var(--var2);
  property3: var(--var3);
  /* ... many more */
}

/* Better: use variables for repeated values */
.element {
  --primary-color: blue;
  --spacing: 10px;

  color: var(--primary-color);
  margin: var(--spacing);
  padding: var(--spacing);
}
```

### 2. Use CSS Custom Properties for Theming

```css
/* Define theme variables at the root */
:root {
  --primary-color: blue;
  --secondary-color: green;
  --text-color: black;
  --background-color: white;
}

/* Use variables throughout the stylesheet */
.element {
  color: var(--text-color);
  background-color: var(--background-color);
}

/* Change theme by updating variables */
.dark-theme {
  --primary-color: lightblue;
  --secondary-color: lightgreen;
  --text-color: white;
  --background-color: black;
}
```

## Best Practices

1. Minimize HTTP requests by combining CSS files
2. Use CSS minification in production
3. Implement critical CSS for above-the-fold content
4. Avoid expensive selectors and properties
5. Use GPU-accelerated properties for animations
6. Implement responsive images with srcset and sizes
7. Use CSS variables judiciously
8. Test performance with browser developer tools
9. Consider using a CSS preprocessor for better organization
10. Implement lazy loading for non-critical CSS

## Next Steps

- Learn about [Browser Compatibility](19-browser-compatibility.md)
- Study [CSS Frameworks and Libraries](20-frameworks.md)
- Explore [Advanced CSS Techniques](21-advanced-techniques.md)
