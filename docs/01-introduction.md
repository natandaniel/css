# Introduction to CSS

CSS (Cascading Style Sheets) is a language used to style and layout web pages. It describes how HTML elements should be displayed on screen, paper, or in other media.

## What is CSS?

CSS is a style sheet language that:

- Controls the visual presentation of HTML documents
- Separates content (HTML) from presentation (CSS)
- Allows for consistent styling across multiple pages
- Makes websites responsive and interactive

## How CSS Works

1. **Selectors**: Target HTML elements you want to style
2. **Properties**: Define what aspects of the element to style
3. **Values**: Specify how to style the selected elements

## Ways to Include CSS

### 1. Inline CSS

```html
<p style="color: blue; font-size: 16px;">This is a blue paragraph</p>
```

### 2. Internal CSS

```html
<head>
  <style>
    p {
      color: blue;
      font-size: 16px;
    }
  </style>
</head>
```

### 3. External CSS (Recommended)

```html
<head>
  <link rel="stylesheet" href="styles.css" />
</head>
```

## Basic CSS Syntax

```css
selector {
  property: value;
  another-property: value;
}
```

Example:

```css
p {
  color: blue;
  font-size: 16px;
  margin: 10px;
}
```

## CSS Comments

```css
/* This is a single-line comment */

/* This is a
   multi-line
   comment */
```

## CSS Units

- **Absolute Units**:

  - `px` (pixels)
  - `pt` (points)
  - `in` (inches)
  - `cm` (centimeters)

- **Relative Units**:
  - `%` (percentage)
  - `em` (relative to parent element)
  - `rem` (relative to root element)
  - `vw` (viewport width)
  - `vh` (viewport height)

## Best Practices

1. Use external CSS files for better maintainability
2. Follow a consistent naming convention
3. Keep selectors simple and specific
4. Use comments to document complex styles
5. Organize related styles together

## Next Steps

- Learn about [CSS Selectors](02-syntax-selectors.md)
- Understand the [Box Model](03-box-model.md)
- Explore [Colors and Backgrounds](04-colors-backgrounds.md)
