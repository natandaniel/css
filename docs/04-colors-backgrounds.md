# Colors and Backgrounds

CSS provides various ways to specify colors and create rich background effects.

## Color Values

### 1. Named Colors

```css
.text {
  color: red;
  color: blue;
  color: transparent;
}
```

### 2. RGB/RGBA

```css
.text {
  color: rgb(255, 0, 0); /* Red */
  color: rgba(255, 0, 0, 0.5); /* Semi-transparent red */
}
```

### 3. Hexadecimal

```css
.text {
  color: #ff0000; /* Red */
  color: #f00; /* Red (shorthand) */
  color: #ff0000ff; /* Red with alpha */
}
```

### 4. HSL/HSLA

```css
.text {
  color: hsl(0, 100%, 50%); /* Red */
  color: hsla(0, 100%, 50%, 0.5); /* Semi-transparent red */
}
```

## Background Properties

### 1. Background Color

```css
.element {
  background-color: #f0f0f0;
}
```

### 2. Background Image

```css
.element {
  background-image: url("image.jpg");
}
```

### 3. Background Repeat

```css
.element {
  background-repeat: no-repeat;
  background-repeat: repeat-x;
  background-repeat: repeat-y;
  background-repeat: space;
  background-repeat: round;
}
```

### 4. Background Position

```css
.element {
  background-position: center;
  background-position: top left;
  background-position: 50% 50%;
  background-position: 20px 50px;
}
```

### 5. Background Size

```css
.element {
  background-size: cover;
  background-size: contain;
  background-size: 100% 100%;
  background-size: 300px 200px;
}
```

### 6. Background Attachment

```css
.element {
  background-attachment: scroll;
  background-attachment: fixed;
  background-attachment: local;
}
```

## Background Shorthand

```css
.element {
  background: #f0f0f0 url("image.jpg") no-repeat center/cover fixed;
  /* color image repeat position/size attachment */
}
```

## Multiple Backgrounds

```css
.element {
  background: url("overlay.png"), url("background.jpg");
  background-size: cover, cover;
  background-position: center, center;
}
```

## Gradients

### 1. Linear Gradient

```css
.element {
  background: linear-gradient(to right, red, blue);
  background: linear-gradient(45deg, red, blue);
  background: linear-gradient(to right, red 20%, blue 80%);
}
```

### 2. Radial Gradient

```css
.element {
  background: radial-gradient(circle, red, blue);
  background: radial-gradient(ellipse at center, red, blue);
}
```

### 3. Conic Gradient

```css
.element {
  background: conic-gradient(from 45deg, red, blue);
  background: conic-gradient(from 45deg at 50% 50%, red, blue);
}
```

## Best Practices

1. Use semantic color names with CSS variables
2. Ensure sufficient color contrast for accessibility
3. Optimize background images for performance
4. Consider using modern image formats (WebP)
5. Use gradients for subtle effects instead of images when possible

## Next Steps

- Learn about [Display Properties](05-display-properties.md)
- Study [Positioning](06-positioning.md)
- Explore [Flexbox](07-flexbox.md)
