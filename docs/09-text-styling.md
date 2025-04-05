# Text Styling

CSS provides a wide range of properties to control the appearance of text, from basic formatting to advanced typography features.

## Text Formatting

### 1. Text Color

```css
.text {
  color: #333;
  color: rgb(51, 51, 51);
  color: hsl(0, 0%, 20%);
}
```

### 2. Text Alignment

```css
.text {
  text-align: left; /* Default */
  text-align: center;
  text-align: right;
  text-align: justify;
}
```

### 3. Text Decoration

```css
.text {
  text-decoration: none; /* Default */
  text-decoration: underline;
  text-decoration: line-through;
  text-decoration: overline;

  /* Multiple decorations */
  text-decoration: underline overline;

  /* Style, color, and thickness */
  text-decoration: underline wavy red;
}
```

### 4. Text Transformation

```css
.text {
  text-transform: none; /* Default */
  text-transform: uppercase;
  text-transform: lowercase;
  text-transform: capitalize;
}
```

### 5. Text Indentation

```css
.text {
  text-indent: 50px;
  text-indent: 2em;
  text-indent: 10%;
}
```

## Text Spacing

### 1. Letter Spacing

```css
.text {
  letter-spacing: normal; /* Default */
  letter-spacing: 2px;
  letter-spacing: -1px;
}
```

### 2. Word Spacing

```css
.text {
  word-spacing: normal; /* Default */
  word-spacing: 5px;
  word-spacing: -2px;
}
```

### 3. Line Height

```css
.text {
  line-height: normal; /* Default */
  line-height: 1.5;
  line-height: 24px;
  line-height: 2em;
}
```

### 4. White Space

```css
.text {
  white-space: normal; /* Default */
  white-space: nowrap;
  white-space: pre;
  white-space: pre-wrap;
  white-space: pre-line;
}
```

## Text Overflow

### 1. Text Overflow

```css
.text {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

### 2. Multiple Line Ellipsis

```css
.text {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
```

## Text Selection

### 1. User Selection

```css
.text {
  user-select: none;
  user-select: text;
  user-select: all;
}
```

### 2. Selection Styling

```css
.text::selection {
  background-color: yellow;
  color: black;
}
```

## Vertical Alignment

### 1. Vertical Align

```css
.text {
  vertical-align: baseline; /* Default */
  vertical-align: top;
  vertical-align: middle;
  vertical-align: bottom;
  vertical-align: 10px;
}
```

## Text Direction

### 1. Writing Mode

```css
.text {
  writing-mode: horizontal-tb; /* Default */
  writing-mode: vertical-rl;
  writing-mode: vertical-lr;
}
```

### 2. Text Direction

```css
.text {
  direction: ltr; /* Default */
  direction: rtl;
}
```

## Best Practices

1. Use relative units (em, rem) for font sizes
2. Maintain sufficient line height for readability
3. Ensure adequate contrast between text and background
4. Use appropriate text alignment for different content types
5. Consider text overflow for responsive designs

## Next Steps

- Learn about [Fonts](10-fonts.md)
- Study [Transitions and Animations](11-transitions-animations.md)
- Explore [Transforms](12-transforms.md)
