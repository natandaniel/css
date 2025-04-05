# Media Queries

Media queries allow you to apply CSS rules based on device characteristics like screen size, orientation, and resolution.

## Basic Syntax

```css
@media media-type and (media-feature) {
  /* CSS rules */
}
```

## Media Types

```css
/* All devices */
@media all {
  /* CSS rules */
}

/* Print devices */
@media print {
  /* CSS rules */
}

/* Screen devices */
@media screen {
  /* CSS rules */
}

/* Speech devices */
@media speech {
  /* CSS rules */
}
```

## Common Media Features

### 1. Width and Height

```css
/* Minimum width */
@media (min-width: 768px) {
  /* CSS rules for screens wider than 768px */
}

/* Maximum width */
@media (max-width: 767px) {
  /* CSS rules for screens narrower than 768px */
}

/* Width range */
@media (min-width: 768px) and (max-width: 1023px) {
  /* CSS rules for screens between 768px and 1023px */
}

/* Height */
@media (min-height: 500px) {
  /* CSS rules for screens taller than 500px */
}
```

### 2. Orientation

```css
/* Portrait orientation */
@media (orientation: portrait) {
  /* CSS rules for portrait mode */
}

/* Landscape orientation */
@media (orientation: landscape) {
  /* CSS rules for landscape mode */
}
```

### 3. Resolution

```css
/* Minimum resolution */
@media (min-resolution: 2dppx) {
  /* CSS rules for high-resolution displays */
}

/* Maximum resolution */
@media (max-resolution: 1dppx) {
  /* CSS rules for standard-resolution displays */
}
```

### 4. Aspect Ratio

```css
/* Minimum aspect ratio */
@media (min-aspect-ratio: 16/9) {
  /* CSS rules for widescreen displays */
}

/* Maximum aspect ratio */
@media (max-aspect-ratio: 4/3) {
  /* CSS rules for standard displays */
}
```

### 5. Color and Color Depth

```css
/* Color support */
@media (color) {
  /* CSS rules for color displays */
}

/* Color depth */
@media (min-color: 8) {
  /* CSS rules for displays with at least 8-bit color */
}
```

### 6. Hover and Pointer

```css
/* Hover capability */
@media (hover: hover) {
  /* CSS rules for devices with hover capability */
}

/* Pointer type */
@media (pointer: fine) {
  /* CSS rules for devices with precise pointing */
}
```

## Common Breakpoints

```css
/* Mobile devices */
@media (max-width: 767px) {
  /* Mobile styles */
}

/* Tablets */
@media (min-width: 768px) and (max-width: 1023px) {
  /* Tablet styles */
}

/* Desktops */
@media (min-width: 1024px) {
  /* Desktop styles */
}

/* Large screens */
@media (min-width: 1440px) {
  /* Large screen styles */
}
```

## Common Use Cases

### 1. Responsive Navigation

```css
/* Mobile navigation */
.nav {
  display: flex;
  flex-direction: column;
}

/* Desktop navigation */
@media (min-width: 768px) {
  .nav {
    flex-direction: row;
  }
}
```

### 2. Responsive Grid

```css
/* Mobile grid */
.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 20px;
}

/* Tablet grid */
@media (min-width: 768px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Desktop grid */
@media (min-width: 1024px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

### 3. Responsive Typography

```css
/* Base font size */
html {
  font-size: 16px;
}

/* Larger font size for larger screens */
@media (min-width: 768px) {
  html {
    font-size: 18px;
  }
}

/* Even larger for very large screens */
@media (min-width: 1440px) {
  html {
    font-size: 20px;
  }
}
```

### 4. Responsive Images

```css
/* Mobile image */
.image {
  width: 100%;
  height: auto;
}

/* Desktop image */
@media (min-width: 768px) {
  .image {
    width: 50%;
    float: left;
    margin-right: 20px;
  }
}
```

## Best Practices

1. Use mobile-first approach
2. Choose breakpoints based on content, not devices
3. Use relative units (rem, em, %) instead of fixed pixels
4. Test on real devices when possible
5. Consider using CSS custom properties for breakpoints

## Next Steps

- Learn about [Responsive Images](15-responsive-images.md)
- Study [Mobile-First Design](16-mobile-first.md)
- Explore [CSS Organization](17-organization.md)
