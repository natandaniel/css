# Fonts and Web Typography

CSS provides extensive control over typography, allowing you to specify font families, sizes, weights, and more.

## Font Family

### 1. Font Family

```css
.text {
  font-family: Arial, sans-serif;
  font-family: "Times New Roman", serif;
  font-family: "Courier New", monospace;
}
```

### 2. Font Stack

```css
.text {
  /* System fonts */
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica,
    Arial, sans-serif;

  /* Web-safe fonts */
  font-family: Georgia, "Times New Roman", Times, serif;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
```

## Font Properties

### 1. Font Size

```css
.text {
  font-size: 16px; /* Absolute */
  font-size: 1.2rem; /* Relative to root */
  font-size: 1.2em; /* Relative to parent */
  font-size: 120%; /* Percentage */
  font-size: larger; /* Keyword */
}
```

### 2. Font Weight

```css
.text {
  font-weight: normal; /* 400 */
  font-weight: bold; /* 700 */
  font-weight: 100; /* Thin */
  font-weight: 900; /* Black */
}
```

### 3. Font Style

```css
.text {
  font-style: normal; /* Default */
  font-style: italic;
  font-style: oblique;
}
```

### 4. Font Variant

```css
.text {
  font-variant: normal; /* Default */
  font-variant: small-caps;
  font-variant: all-small-caps;
}
```

### 5. Font Shorthand

```css
.text {
  font: italic bold 16px/1.5 Arial, sans-serif;
  /* style weight size/line-height family */
}
```

## Web Fonts

### 1. @font-face

```css
@font-face {
  font-family: "MyCustomFont";
  src: url("path/to/font.woff2") format("woff2"), url("path/to/font.woff")
      format("woff");
  font-weight: normal;
  font-style: normal;
  font-display: swap;
}
```

### 2. Google Fonts

```html
<!-- In HTML -->
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
  rel="stylesheet"
/>

<!-- In CSS -->
.text { font-family: 'Roboto', sans-serif; }
```

### 3. Font Display

```css
@font-face {
  font-display: auto; /* Default */
  font-display: block; /* Block text until font loads */
  font-display: swap; /* Show fallback until font loads */
  font-display: fallback; /* Short block period then swap */
  font-display: optional; /* Use fallback if font takes too long */
}
```

## Font Features

### 1. Font Feature Settings

```css
.text {
  font-feature-settings: "liga" 1; /* Ligatures */
  font-feature-settings: "kern" 1; /* Kerning */
  font-feature-settings: "tnum" 1; /* Tabular numbers */
  font-feature-settings: "frac" 1; /* Fractions */
}
```

### 2. Font Variant Numeric

```css
.text {
  font-variant-numeric: normal; /* Default */
  font-variant-numeric: tabular-nums; /* Monospace numbers */
  font-variant-numeric: oldstyle-nums; /* Old-style numbers */
  font-variant-numeric: proportional-nums; /* Proportional numbers */
}
```

## Font Loading

### 1. Preload

```html
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin />
```

### 2. Font Loading API

```javascript
// JavaScript
if ("fonts" in document) {
  Promise.all([
    document.fonts.load("1em MyCustomFont"),
    document.fonts.load("bold 1em MyCustomFont"),
  ]).then(() => {
    // Fonts loaded
  });
}
```

## Best Practices

1. Use a comprehensive font stack with fallbacks
2. Specify font-display strategy for web fonts
3. Use relative units for font sizes
4. Limit the number of font weights and styles
5. Consider performance when using web fonts

## Next Steps

- Learn about [Transitions and Animations](11-transitions-animations.md)
- Study [Transforms](12-transforms.md)
- Explore [Shadows and Filters](13-shadows-filters.md)
