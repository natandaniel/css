# Positioning

CSS positioning allows you to control the layout of elements by taking them out of the normal document flow and placing them precisely where you want them.

## Position Property

The `position` property specifies how an element is positioned in the document.

### 1. Static (Default)

```css
.element {
  position: static;
}
```

- Default positioning
- Follows normal document flow
- Ignores top, right, bottom, left properties

### 2. Relative

```css
.element {
  position: relative;
  top: 10px;
  left: 20px;
}
```

- Positioned relative to its normal position
- Maintains space in document flow
- Can use top, right, bottom, left properties
- Creates a positioning context for absolute children

### 3. Absolute

```css
.element {
  position: absolute;
  top: 0;
  right: 0;
}
```

- Positioned relative to nearest positioned ancestor
- Removed from normal document flow
- Can use top, right, bottom, left properties
- If no positioned ancestor, positioned relative to viewport

### 4. Fixed

```css
.element {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

- Positioned relative to viewport
- Stays in place during scrolling
- Removed from normal document flow
- Can use top, right, bottom, left properties

### 5. Sticky

```css
.element {
  position: sticky;
  top: 0;
}
```

- Toggles between relative and fixed
- Sticks when scrolling reaches specified threshold
- Requires a threshold value (top, right, bottom, left)
- Parent container must have sufficient height

## Positioning Context

### Creating a Positioning Context

```css
.parent {
  position: relative; /* Creates positioning context */
}

.child {
  position: absolute;
  top: 0;
  left: 0;
}
```

### Z-Index

```css
.element {
  z-index: 1; /* Higher values appear on top */
}
```

- Controls stacking order of positioned elements
- Only works on positioned elements
- Higher values appear on top
- Can be negative

## Common Use Cases

### 1. Modal Dialog

```css
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1000;
}
```

### 2. Sticky Header

```css
.header {
  position: sticky;
  top: 0;
  z-index: 100;
}
```

### 3. Tooltip

```css
.tooltip {
  position: absolute;
  top: -20px;
  left: 50%;
  transform: translateX(-50%);
}
```

### 4. Fixed Navigation

```css
.nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 50;
}
```

## Best Practices

1. Use relative positioning for creating positioning contexts
2. Avoid fixed positioning for important content
3. Use z-index sparingly and keep values manageable
4. Consider mobile devices when using fixed positioning
5. Test sticky positioning across browsers

## Next Steps

- Learn about [Flexbox](07-flexbox.md)
- Study [Grid](08-grid.md)
- Explore [Text Styling](09-text-styling.md)
