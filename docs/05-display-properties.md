# Display Properties

The `display` property is one of the most important CSS properties for controlling layout. It determines how an element is rendered in the document flow.

## Common Display Values

### 1. Block

```css
.element {
  display: block;
}
```

- Takes full width available
- Starts on a new line
- Respects width and height
- Examples: `<div>`, `<p>`, `<section>`

### 2. Inline

```css
.element {
  display: inline;
}
```

- Takes only necessary width
- Doesn't start on a new line
- Ignores width and height
- Examples: `<span>`, `<a>`, `<em>`

### 3. Inline-Block

```css
.element {
  display: inline-block;
}
```

- Combines features of both block and inline
- Doesn't start on a new line
- Respects width and height
- Useful for horizontal lists and grids

### 4. None

```css
.element {
  display: none;
}
```

- Removes element from document flow
- Takes no space
- Not accessible to screen readers
- Use `visibility: hidden` to maintain layout

## Modern Display Values

### 1. Flex

```css
.container {
  display: flex;
}
```

- Creates a flex container
- Enables flexible box layout
- See [Flexbox](07-flexbox.md) for details

### 2. Grid

```css
.container {
  display: grid;
}
```

- Creates a grid container
- Enables CSS Grid layout
- See [Grid](08-grid.md) for details

### 3. Table

```css
.element {
  display: table;
  display: table-cell;
  display: table-row;
}
```

- Mimics table layout
- Useful for vertical alignment
- Legacy approach, prefer flex/grid

## Special Display Values

### 1. Contents

```css
.element {
  display: contents;
}
```

- Makes container "disappear"
- Children become direct children of parent
- Useful for semantic grouping

### 2. Flow-Root

```css
.element {
  display: flow-root;
}
```

- Creates a new block formatting context
- Alternative to `overflow: hidden`
- Better for containing floats

## Display and Visibility

```css
.element {
  /* Hide element but maintain layout */
  visibility: hidden;

  /* Show element */
  visibility: visible;

  /* Hide element and remove from layout */
  display: none;
}
```

## Best Practices

1. Use semantic HTML elements with default display values
2. Prefer modern layout methods (flex/grid) over table display
3. Use `display: none` for hiding elements completely
4. Use `visibility: hidden` when maintaining layout is important
5. Consider accessibility when hiding elements

## Next Steps

- Learn about [Positioning](06-positioning.md)
- Study [Flexbox](07-flexbox.md)
- Explore [Grid](08-grid.md)
