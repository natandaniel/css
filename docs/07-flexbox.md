# Flexbox

Flexbox (Flexible Box Layout) is a one-dimensional layout method for arranging items in rows or columns. It provides a more efficient way to distribute space and align items.

## Basic Concepts

### Container Properties

```css
.container {
  display: flex; /* or display: inline-flex */
}
```

### Main Axis and Cross Axis

- Main axis: defined by `flex-direction`
- Cross axis: perpendicular to main axis

## Container Properties

### 1. Flex Direction

```css
.container {
  flex-direction: row; /* Default */
  flex-direction: row-reverse; /* Right to left */
  flex-direction: column; /* Top to bottom */
  flex-direction: column-reverse; /* Bottom to top */
}
```

### 2. Justify Content (Main Axis)

```css
.container {
  justify-content: flex-start; /* Default */
  justify-content: flex-end; /* End of container */
  justify-content: center; /* Center */
  justify-content: space-between; /* Equal space between */
  justify-content: space-around; /* Equal space around */
  justify-content: space-evenly; /* Equal space between and around */
}
```

### 3. Align Items (Cross Axis)

```css
.container {
  align-items: stretch; /* Default */
  align-items: flex-start; /* Start of cross axis */
  align-items: flex-end; /* End of cross axis */
  align-items: center; /* Center */
  align-items: baseline; /* Text baseline */
}
```

### 4. Flex Wrap

```css
.container {
  flex-wrap: nowrap; /* Default */
  flex-wrap: wrap; /* Wrap to next line */
  flex-wrap: wrap-reverse; /* Wrap to previous line */
}
```

### 5. Align Content (Multiple Lines)

```css
.container {
  align-content: flex-start;
  align-content: flex-end;
  align-content: center;
  align-content: space-between;
  align-content: space-around;
  align-content: stretch; /* Default */
}
```

## Item Properties

### 1. Flex Grow

```css
.item {
  flex-grow: 0; /* Default */
  flex-grow: 1; /* Grow to fill space */
}
```

### 2. Flex Shrink

```css
.item {
  flex-shrink: 1; /* Default */
  flex-shrink: 0; /* Don't shrink */
}
```

### 3. Flex Basis

```css
.item {
  flex-basis: auto; /* Default */
  flex-basis: 0; /* Start from zero */
  flex-basis: 100px; /* Start from 100px */
}
```

### 4. Flex Shorthand

```css
.item {
  flex: 0 1 auto; /* Default */
  flex: 1; /* flex-grow: 1, flex-shrink: 1, flex-basis: 0% */
  flex: auto; /* flex-grow: 1, flex-shrink: 1, flex-basis: auto */
  flex: none; /* flex-grow: 0, flex-shrink: 0, flex-basis: auto */
}
```

### 5. Align Self

```css
.item {
  align-self: auto; /* Default */
  align-self: flex-start; /* Start of cross axis */
  align-self: flex-end; /* End of cross axis */
  align-self: center; /* Center */
  align-self: stretch; /* Stretch to fill */
}
```

## Common Use Cases

### 1. Navigation Bar

```css
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### 2. Card Layout

```css
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.card {
  flex: 1 1 300px;
}
```

### 3. Centered Content

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

### 4. Equal Height Columns

```css
.columns {
  display: flex;
}

.column {
  flex: 1;
}
```

## Best Practices

1. Use `flex: 1` for equal distribution of space
2. Use `flex-wrap: wrap` for responsive layouts
3. Use `gap` property for consistent spacing
4. Use `align-items: center` for vertical centering
5. Use `flex-shrink: 0` to prevent unwanted shrinking

## Next Steps

- Learn about [Grid](08-grid.md)
- Study [Text Styling](09-text-styling.md)
- Explore [Fonts](10-fonts.md)
