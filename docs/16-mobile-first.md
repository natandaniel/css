# Mobile-First Design

Mobile-first design is a design approach that starts with the mobile experience and progressively enhances it for larger screens.

## Core Principles

1. Start with mobile layout
2. Use progressive enhancement
3. Design for touch first
4. Optimize for performance
5. Consider mobile constraints

## Basic Structure

### 1. Viewport Meta Tag

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### 2. Base Styles

```css
/* Mobile-first base styles */
:root {
  --base-font-size: 16px;
  --spacing-unit: 1rem;
}

body {
  font-size: var(--base-font-size);
  line-height: 1.5;
  margin: 0;
  padding: 0;
}

/* Container */
.container {
  width: 100%;
  padding: 0 var(--spacing-unit);
  margin: 0 auto;
}
```

## Responsive Typography

### 1. Fluid Typography

```css
/* Mobile typography */
html {
  font-size: 16px;
}

/* Tablet typography */
@media (min-width: 768px) {
  html {
    font-size: 18px;
  }
}

/* Desktop typography */
@media (min-width: 1024px) {
  html {
    font-size: 20px;
  }
}
```

### 2. Responsive Headings

```css
h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

@media (min-width: 768px) {
  h1 {
    font-size: 2.5rem;
  }
}

@media (min-width: 1024px) {
  h1 {
    font-size: 3rem;
  }
}
```

## Layout Patterns

### 1. Single Column Layout

```css
/* Mobile layout */
.content {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-unit);
}

/* Tablet layout */
@media (min-width: 768px) {
  .content {
    flex-direction: row;
    flex-wrap: wrap;
  }

  .content > * {
    flex: 1 1 45%;
  }
}

/* Desktop layout */
@media (min-width: 1024px) {
  .content > * {
    flex: 1 1 30%;
  }
}
```

### 2. Navigation

```css
/* Mobile navigation */
.nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: white;
  padding: 1rem;
  box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
}

/* Desktop navigation */
@media (min-width: 768px) {
  .nav {
    position: static;
    box-shadow: none;
  }
}
```

### 3. Grid Systems

```css
/* Mobile grid */
.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-unit);
}

/* Tablet grid */
@media (min-width: 768px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Desktop grid */
@media (min-width: 1024px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

## Touch-Friendly Design

### 1. Touch Targets

```css
/* Mobile touch targets */
.button {
  min-height: 44px;
  min-width: 44px;
  padding: 0.5rem 1rem;
}

/* Desktop buttons */
@media (min-width: 768px) {
  .button {
    min-height: 36px;
    min-width: 36px;
  }
}
```

### 2. Spacing

```css
/* Mobile spacing */
.element {
  margin: 1rem 0;
  padding: 1rem;
}

/* Desktop spacing */
@media (min-width: 768px) {
  .element {
    margin: 2rem 0;
    padding: 2rem;
  }
}
```

## Performance Optimization

### 1. Image Loading

```css
/* Mobile images */
.image {
  width: 100%;
  height: auto;
}

/* Desktop images */
@media (min-width: 768px) {
  .image {
    max-width: 50%;
  }
}
```

### 2. Conditional Loading

```css
/* Hide desktop elements on mobile */
.desktop-only {
  display: none;
}

/* Show desktop elements on larger screens */
@media (min-width: 768px) {
  .desktop-only {
    display: block;
  }
}
```

## Common Patterns

### 1. Card Layout

```css
/* Mobile cards */
.card {
  padding: 1rem;
  margin-bottom: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Desktop cards */
@media (min-width: 768px) {
  .card {
    padding: 2rem;
    margin-bottom: 2rem;
  }
}
```

### 2. Form Elements

```css
/* Mobile forms */
.form-group {
  margin-bottom: 1rem;
}

input,
select,
textarea {
  width: 100%;
  padding: 0.5rem;
  font-size: 16px; /* Prevent zoom on iOS */
}

/* Desktop forms */
@media (min-width: 768px) {
  .form-group {
    margin-bottom: 2rem;
  }

  input,
  select,
  textarea {
    max-width: 500px;
  }
}
```

## Best Practices

1. Use relative units (rem, em, %) instead of fixed pixels
2. Implement touch-friendly navigation
3. Optimize images for mobile
4. Test on real devices
5. Consider mobile performance
6. Use appropriate breakpoints
7. Implement progressive enhancement

## Next Steps

- Learn about [CSS Organization](17-organization.md)
- Study [Performance Optimization](18-performance.md)
- Explore [Browser Compatibility](19-browser-compatibility.md)
