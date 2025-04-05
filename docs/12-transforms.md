# Transforms

CSS transforms allow you to modify the coordinate space of an element, enabling rotation, scaling, skewing, and translation.

## 2D Transforms

### 1. Translate

```css
.element {
  transform: translate(100px, 50px); /* Move right and down */
  transform: translateX(100px); /* Move right */
  transform: translateY(50px); /* Move down */
}
```

### 2. Scale

```css
.element {
  transform: scale(2); /* Double size */
  transform: scale(2, 0.5); /* Double width, half height */
  transform: scaleX(2); /* Double width */
  transform: scaleY(0.5); /* Half height */
}
```

### 3. Rotate

```css
.element {
  transform: rotate(45deg); /* Rotate 45 degrees clockwise */
  transform: rotate(-45deg); /* Rotate 45 degrees counterclockwise */
}
```

### 4. Skew

```css
.element {
  transform: skew(10deg, 5deg); /* Skew both axes */
  transform: skewX(10deg); /* Skew horizontally */
  transform: skewY(5deg); /* Skew vertically */
}
```

### 5. Matrix

```css
.element {
  transform: matrix(1, 0, 0, 1, 100, 50); /* Complex transformations */
}
```

## 3D Transforms

### 1. Perspective

```css
.container {
  perspective: 1000px; /* Add depth */
}

.element {
  transform: rotateY(45deg); /* Rotate around Y axis */
}
```

### 2. 3D Translation

```css
.element {
  transform: translate3d(100px, 50px, 0);
  transform: translateZ(100px); /* Move along Z axis */
}
```

### 3D Rotation

```css
.element {
  transform: rotateX(45deg); /* Rotate around X axis */
  transform: rotateY(45deg); /* Rotate around Y axis */
  transform: rotateZ(45deg); /* Rotate around Z axis */
  transform: rotate3d(1, 1, 1, 45deg); /* Rotate around arbitrary axis */
}
```

### 4. 3D Scaling

```css
.element {
  transform: scale3d(2, 1, 1); /* Scale in 3D space */
  transform: scaleZ(2); /* Scale along Z axis */
}
```

## Transform Origin

```css
.element {
  transform-origin: center; /* Default */
  transform-origin: top left; /* Top-left corner */
  transform-origin: 50% 50%; /* Center */
  transform-origin: 0 0; /* Top-left corner */
  transform-origin: 100% 100%; /* Bottom-right corner */
}
```

## Multiple Transforms

```css
.element {
  transform: translate(100px, 50px) rotate(45deg) scale(1.5);
}
```

## Common Use Cases

### 1. Centering Elements

```css
.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### 2. Hover Effects

```css
.card {
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-10px);
}
```

### 3. 3D Card Flip

```css
.card {
  transform-style: preserve-3d;
  transition: transform 0.6s;
}

.card:hover {
  transform: rotateY(180deg);
}

.front,
.back {
  position: absolute;
  backface-visibility: hidden;
}

.back {
  transform: rotateY(180deg);
}
```

### 4. Parallax Effect

```css
.parallax {
  transform: translateZ(-1px) scale(2);
  z-index: -1;
}
```

## Performance Considerations

### 1. GPU Acceleration

```css
.element {
  transform: translateZ(0); /* Force GPU acceleration */
  will-change: transform; /* Hint for browser */
}
```

### 2. Transform vs Position

```css
/* Prefer transform over position for animations */
.element {
  transform: translateX(100px); /* Better performance */
}

.element {
  left: 100px; /* Worse performance */
}
```

## Best Practices

1. Use transforms instead of position properties for animations
2. Keep transform origin in mind when rotating or scaling
3. Use perspective for 3D effects
4. Consider browser compatibility for 3D transforms
5. Use will-change for complex animations

## Next Steps

- Learn about [Shadows and Filters](13-shadows-filters.md)
- Study [Media Queries](14-media-queries.md)
- Explore [Responsive Images](15-responsive-images.md)
