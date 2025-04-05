# Browser Compatibility

Ensuring your CSS works across different browsers is essential for a consistent user experience. This guide covers techniques for handling browser compatibility issues.

## Vendor Prefixes

### 1. Common Vendor Prefixes

```css
/* Standard property */
.element {
  transform: rotate(45deg);

  /* Vendor prefixes */
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
```

### 2. Using Autoprefixer

```css
/* Input */
.element {
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s ease;
}

/* Output (with autoprefixer) */
.element {
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  -webkit-align-items: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-justify-content: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-transition: -webkit-transform 0.3s ease;
  transition: -webkit-transform 0.3s ease;
  -o-transition: transform 0.3s ease;
  transition: transform 0.3s ease;
  transition: transform 0.3s ease, -webkit-transform 0.3s ease;
}
```

## Feature Detection

### 1. @supports Rule

```css
/* Check for CSS Grid support */
@supports (display: grid) {
  .container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
}

/* Fallback for browsers without Grid */
@supports not (display: grid) {
  .container {
    display: flex;
    flex-wrap: wrap;
  }

  .container > * {
    flex: 1 1 33.333%;
  }
}
```

### 2. Feature Queries for Flexbox

```css
/* Check for Flexbox support */
@supports (display: flex) {
  .nav {
    display: flex;
    justify-content: space-between;
  }
}

/* Fallback for older browsers */
@supports not (display: flex) {
  .nav {
    display: block;
    text-align: center;
  }

  .nav > * {
    display: inline-block;
    margin: 0 10px;
  }
}
```

## Polyfills and Fallbacks

### 1. CSS Grid Fallbacks

```css
/* Modern browsers */
@supports (display: grid) {
  .grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }
}

/* Older browsers */
@supports not (display: grid) {
  .grid {
    display: flex;
    flex-wrap: wrap;
    margin: -10px;
  }

  .grid > * {
    flex: 1 1 33.333%;
    padding: 10px;
    box-sizing: border-box;
  }
}
```

### 2. CSS Variables Fallbacks

```css
/* Modern browsers */
:root {
  --primary-color: blue;
  --secondary-color: green;
}

.button {
  background-color: var(--primary-color, blue);
  color: var(--secondary-color, green);
}

/* Older browsers */
.button {
  background-color: blue;
  color: green;
}
```

## Browser-Specific Hacks

### 1. IE-Specific Hacks

```css
/* IE 10+ */
@media all and (-ms-high-contrast: none), (-ms-high-contrast: active) {
  .element {
    /* IE-specific styles */
  }
}

/* IE 9 */
.element {
  /* Standard styles */
  background-color: blue;

  /* IE 9 specific */
  background-color: blue\9;
}
```

### 2. Firefox-Specific Hacks

```css
/* Firefox only */
@-moz-document url-prefix() {
  .element {
    /* Firefox-specific styles */
  }
}
```

### 3. Safari-Specific Hacks

```css
/* Safari only */
@media not all and (min-resolution: 0.001dpcm) {
  @supports (-webkit-appearance: none) {
    .element {
      /* Safari-specific styles */
    }
  }
}
```

## Common Compatibility Issues

### 1. Flexbox Issues

```css
/* Fix for older IE */
.flex-container {
  display: -ms-flexbox;
  display: flex;
  -ms-flex-direction: row;
  flex-direction: row;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
}

.flex-item {
  -ms-flex: 1 1 auto;
  flex: 1 1 auto;
}
```

### 2. Grid Issues

```css
/* Fallback for browsers without Grid */
.grid-container {
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: 1fr 1fr 1fr;
  grid-template-columns: repeat(3, 1fr);
}

/* Fallback for older browsers */
@supports not (display: grid) {
  .grid-container {
    display: flex;
    flex-wrap: wrap;
  }

  .grid-item {
    flex: 1 1 33.333%;
  }
}
```

### 3. CSS Variables Issues

```css
/* Fallback for browsers without CSS variables */
.element {
  background-color: blue; /* Fallback */
  background-color: var(--primary-color, blue);
  color: white; /* Fallback */
  color: var(--text-color, white);
}
```

## Testing and Debugging

### 1. Browser Testing Tools

```css
/* Add a border to identify rendering issues */
.debug * {
  outline: 1px solid red;
}

/* Add a class to identify specific elements */
.debug-element {
  outline: 2px dashed blue;
}
```

### 2. Conditional Comments (for IE)

```html
<!--[if IE]>
  <link rel="stylesheet" href="ie-fixes.css" />
<![endif]-->
```

### 3. Feature Detection with JavaScript

```javascript
// Check for CSS Grid support
if (CSS.supports("display", "grid")) {
  document.documentElement.classList.add("css-grid");
} else {
  document.documentElement.classList.add("no-css-grid");
}
```

## Best Practices

1. Use feature detection instead of browser detection
2. Implement graceful degradation
3. Use polyfills for critical features
4. Test across multiple browsers and devices
5. Use CSS reset or normalize.css
6. Keep vendor prefixes up to date
7. Use modern CSS features with fallbacks
8. Consider using a CSS preprocessor with autoprefixer
9. Document browser-specific hacks
10. Use browser developer tools for debugging

## Next Steps

- Learn about [CSS Frameworks and Libraries](20-frameworks.md)
- Study [Advanced CSS Techniques](21-advanced-techniques.md)
- Explore [CSS Architecture](22-architecture.md)
