# CSS Organization

Proper CSS organization is essential for maintaining scalable and maintainable stylesheets. This guide covers methodologies, file structure, and best practices.

## CSS Methodologies

### 1. BEM (Block Element Modifier)

```css
/* Block */
.card {
}

/* Element */
.card__title {
}
.card__content {
}
.card__footer {
}

/* Modifier */
.card--featured {
}
.card--dark {
}
```

### 2. SMACSS (Scalable and Modular Architecture for CSS)

```css
/* Base */
body,
h1,
p {
}

/* Layout */
.header,
.footer,
.sidebar {
}

/* Module */
.button,
.card,
.modal {
}

/* State */
.is-hidden,
.is-active,
.is-disabled {
}

/* Theme */
.theme-dark,
.theme-light {
}
```

### 3. OOCSS (Object-Oriented CSS)

```css
/* Reusable objects */
.button {
}
.media {
}
.grid {
}

/* Content-specific styles */
.article-button {
}
.product-media {
}
```

## File Structure

### 1. Component-Based Structure

```
styles/
├── base/
│   ├── _reset.css
│   ├── _typography.css
│   └── _variables.css
├── components/
│   ├── _buttons.css
│   ├── _cards.css
│   └── _forms.css
├── layouts/
│   ├── _header.css
│   ├── _footer.css
│   └── _grid.css
├── pages/
│   ├── _home.css
│   └── _about.css
├── themes/
│   ├── _light.css
│   └── _dark.css
└── main.css
```

### 2. Feature-Based Structure

```
styles/
├── features/
│   ├── _navigation.css
│   ├── _authentication.css
│   └── _dashboard.css
├── shared/
│   ├── _variables.css
│   ├── _mixins.css
│   └── _utilities.css
└── main.css
```

## CSS Variables

### 1. Global Variables

```css
:root {
  /* Colors */
  --color-primary: #3498db;
  --color-secondary: #2ecc71;
  --color-text: #333;
  --color-background: #fff;

  /* Typography */
  --font-primary: "Arial", sans-serif;
  --font-size-base: 16px;
  --line-height-base: 1.5;

  /* Spacing */
  --spacing-xs: 0.25rem;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 2rem;

  /* Breakpoints */
  --breakpoint-sm: 576px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 992px;
  --breakpoint-xl: 1200px;
}
```

### 2. Component Variables

```css
.card {
  --card-padding: var(--spacing-md);
  --card-border-radius: 8px;
  --card-background: var(--color-background);
  --card-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

  padding: var(--card-padding);
  border-radius: var(--card-border-radius);
  background: var(--card-background);
  box-shadow: var(--card-shadow);
}
```

## CSS Reset and Normalize

### 1. Basic Reset

```css
/* Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Base styles */
html {
  font-size: 16px;
  line-height: 1.5;
}

body {
  font-family: var(--font-primary);
  color: var(--color-text);
  background: var(--color-background);
}
```

### 2. Using Normalize.css

```css
/* Import normalize.css */
@import "normalize.css";

/* Custom base styles */
body {
  font-family: var(--font-primary);
  color: var(--color-text);
  background: var(--color-background);
}
```

## Utility Classes

### 1. Spacing Utilities

```css
/* Margin utilities */
.m-0 {
  margin: 0;
}
.m-1 {
  margin: var(--spacing-xs);
}
.m-2 {
  margin: var(--spacing-sm);
}
.m-3 {
  margin: var(--spacing-md);
}
.m-4 {
  margin: var(--spacing-lg);
}

/* Padding utilities */
.p-0 {
  padding: 0;
}
.p-1 {
  padding: var(--spacing-xs);
}
.p-2 {
  padding: var(--spacing-sm);
}
.p-3 {
  padding: var(--spacing-md);
}
.p-4 {
  padding: var(--spacing-lg);
}
```

### 2. Display Utilities

```css
/* Display */
.d-none {
  display: none;
}
.d-block {
  display: block;
}
.d-inline {
  display: inline;
}
.d-inline-block {
  display: inline-block;
}
.d-flex {
  display: flex;
}
.d-grid {
  display: grid;
}

/* Flex utilities */
.flex-row {
  flex-direction: row;
}
.flex-column {
  flex-direction: column;
}
.justify-center {
  justify-content: center;
}
.align-center {
  align-items: center;
}
```

### 3. Text Utilities

```css
/* Text alignment */
.text-left {
  text-align: left;
}
.text-center {
  text-align: center;
}
.text-right {
  text-align: right;
}

/* Text colors */
.text-primary {
  color: var(--color-primary);
}
.text-secondary {
  color: var(--color-secondary);
}

/* Font weights */
.fw-normal {
  font-weight: normal;
}
.fw-bold {
  font-weight: bold;
}
```

## Media Queries Organization

### 1. Mobile-First Approach

```css
/* Base styles (mobile) */
.container {
  width: 100%;
  padding: var(--spacing-md);
}

/* Tablet styles */
@media (min-width: 768px) {
  .container {
    max-width: 720px;
    margin: 0 auto;
  }
}

/* Desktop styles */
@media (min-width: 992px) {
  .container {
    max-width: 960px;
  }
}
```

### 2. Using Mixins (Sass)

```scss
// Breakpoint mixins
@mixin tablet {
  @media (min-width: 768px) {
    @content;
  }
}

@mixin desktop {
  @media (min-width: 992px) {
    @content;
  }
}

// Usage
.container {
  width: 100%;
  padding: var(--spacing-md);

  @include tablet {
    max-width: 720px;
    margin: 0 auto;
  }

  @include desktop {
    max-width: 960px;
  }
}
```

## CSS Preprocessors

### 1. Sass/SCSS

```scss
// Variables
$primary-color: #3498db;
$secondary-color: #2ecc71;

// Mixins
@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

// Nesting
.card {
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

  &__title {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
  }

  &__content {
    @include flex-center;
  }

  &--featured {
    border: 2px solid $primary-color;
  }
}
```

### 2. PostCSS

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

## Best Practices

1. Use a consistent naming convention (BEM, SMACSS, etc.)
2. Organize CSS files by component or feature
3. Use CSS variables for reusable values
4. Implement utility classes for common styles
5. Follow a mobile-first approach for responsive design
6. Use CSS preprocessors for advanced features
7. Minimize specificity to avoid conflicts
8. Document complex selectors and hacks
9. Use CSS linting tools to maintain consistency
10. Consider using CSS modules or CSS-in-JS for component isolation

## Next Steps

- Learn about [Performance Optimization](18-performance.md)
- Study [Browser Compatibility](19-browser-compatibility.md)
- Explore [CSS Frameworks and Libraries](20-frameworks.md)
