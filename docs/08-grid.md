# CSS Grid

CSS Grid is a two-dimensional layout system designed for organizing content in rows and columns. It provides precise control over both dimensions simultaneously.

## Basic Concepts

### Grid Container

```css
.container {
  display: grid; /* or display: inline-grid */
}
```

### Grid Lines

- Horizontal lines define rows
- Vertical lines define columns
- Lines are numbered starting from 1

## Container Properties

### 1. Grid Template Columns/Rows

```css
.container {
  /* Define columns */
  grid-template-columns: 100px 1fr 2fr;
  grid-template-columns: repeat(3, 1fr);
  grid-template-columns: minmax(100px, 1fr);

  /* Define rows */
  grid-template-rows: 100px auto;
  grid-template-rows: repeat(2, 1fr);
}
```

### 2. Grid Areas

```css
.container {
  grid-template-areas:
    "header header header"
    "nav main aside"
    "footer footer footer";
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
.aside {
  grid-area: aside;
}
.footer {
  grid-area: footer;
}
```

### 3. Gap

```css
.container {
  gap: 20px; /* Both row and column */
  row-gap: 20px; /* Row gap only */
  column-gap: 20px; /* Column gap only */
}
```

### 4. Justify/Align Items

```css
.container {
  /* Align items horizontally */
  justify-items: start;
  justify-items: end;
  justify-items: center;
  justify-items: stretch; /* Default */

  /* Align items vertically */
  align-items: start;
  align-items: end;
  align-items: center;
  align-items: stretch; /* Default */
}
```

### 5. Justify/Align Content

```css
.container {
  /* Align entire grid horizontally */
  justify-content: start;
  justify-content: end;
  justify-content: center;
  justify-content: space-between;
  justify-content: space-around;
  justify-content: space-evenly;

  /* Align entire grid vertically */
  align-content: start;
  align-content: end;
  align-content: center;
  align-content: space-between;
  align-content: space-around;
  align-content: space-evenly;
}
```

## Item Properties

### 1. Grid Column/Row Start/End

```css
.item {
  /* Column placement */
  grid-column-start: 1;
  grid-column-end: 3;
  grid-column: 1 / 3; /* Shorthand */

  /* Row placement */
  grid-row-start: 1;
  grid-row-end: 3;
  grid-row: 1 / 3; /* Shorthand */
}
```

### 2. Grid Area

```css
.item {
  grid-area: 1 / 1 / 3 / 3; /* row-start / column-start / row-end / column-end */
}
```

### 3. Justify/Align Self

```css
.item {
  /* Align item horizontally */
  justify-self: start;
  justify-self: end;
  justify-self: center;
  justify-self: stretch; /* Default */

  /* Align item vertically */
  align-self: start;
  align-self: end;
  align-self: center;
  align-self: stretch; /* Default */
}
```

## Common Use Cases

### 1. Basic Grid Layout

```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
```

### 2. Responsive Grid

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}
```

### 3. Grid with Named Areas

```css
.layout {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: 200px 1fr;
  grid-template-rows: auto 1fr auto;
}
```

### 4. Overlapping Elements

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
}

.overlap {
  grid-column: 1 / 3;
  grid-row: 1 / 3;
  z-index: 1;
}
```

## Best Practices

1. Use `fr` units for flexible sizing
2. Use `minmax()` for responsive grids
3. Use `auto-fit` or `auto-fill` for dynamic columns
4. Use named areas for complex layouts
5. Use `gap` instead of margins for spacing

## Next Steps

- Learn about [Text Styling](09-text-styling.md)
- Study [Fonts](10-fonts.md)
- Explore [Transitions and Animations](11-transitions-animations.md)
