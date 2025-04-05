# The CSS Box Model

The CSS box model is a fundamental concept that describes how elements are structured and spaced in CSS. Every HTML element is treated as a box with specific properties.

## Box Model Components

```
+------------------------+
|        Margin          |
|  +------------------+  |
|  |     Border       |  |
|  |  +------------+  |  |
|  |  |  Padding   |  |  |
|  |  |  +------+  |  |  |
|  |  |  |Content|  |  |  |
|  |  |  +------+  |  |  |
|  |  +------------+  |  |
|  +------------------+  |
+------------------------+
```

## Content

The actual content of the element (text, images, etc.)

```css
.box {
  width: 300px;
  height: 200px;
}
```

## Padding

Space between content and border

```css
.box {
  padding: 20px; /* All sides */
  padding: 10px 20px; /* Top/bottom, left/right */
  padding: 10px 20px 15px 25px; /* Top, right, bottom, left */
}
```

## Border

The edge of the element

```css
.box {
  border: 1px solid black; /* Shorthand */
  border-width: 1px; /* Width */
  border-style: solid; /* Style */
  border-color: black; /* Color */

  /* Individual sides */
  border-top: 1px solid black;
  border-right: 2px dashed red;
  border-bottom: 1px solid black;
  border-left: 2px dashed red;
}
```

## Margin

Space outside the border

```css
.box {
  margin: 20px; /* All sides */
  margin: 10px 20px; /* Top/bottom, left/right */
  margin: 10px 20px 15px 25px; /* Top, right, bottom, left */
}
```

## Box Sizing

### Content Box (Default)

```css
.box {
  box-sizing: content-box;
  width: 300px; /* Total width = 300px + padding + border */
}
```

### Border Box

```css
.box {
  box-sizing: border-box;
  width: 300px; /* Total width = 300px (includes padding and border) */
}
```

## Common Properties

### Width and Height

```css
.element {
  width: 100px;
  height: 100px;
  max-width: 500px;
  min-height: 50px;
}
```

### Box Shadow

```css
.element {
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
  /* Horizontal offset, vertical offset, blur radius, color */
}
```

## Collapsing Margins

When two elements have margins, they collapse to the larger value:

```css
.box1 {
  margin-bottom: 20px;
}
.box2 {
  margin-top: 30px;
}
/* Result: 30px space between boxes, not 50px */
```

## Best Practices

1. Use `box-sizing: border-box` for predictable layouts
2. Be consistent with margin/padding units
3. Use shorthand properties when possible
4. Consider using CSS custom properties for common values
5. Test layouts across different screen sizes

## Next Steps

- Learn about [Colors and Backgrounds](04-colors-backgrounds.md)
- Study [Display Properties](05-display-properties.md)
- Explore [Positioning](06-positioning.md)
