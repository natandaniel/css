# Shadows and Filters

CSS provides powerful tools for adding depth with shadows and visual effects with filters.

## Box Shadows

Box shadows add depth and dimension to elements.

### 1. Basic Box Shadow

```css
.element {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  /* offset-x offset-y blur-radius color */
}
```

### 2. Inner Shadow

```css
.element {
  box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
  /* inset offset-x offset-y blur-radius color */
}
```

### 3. Multiple Shadows

```css
.element {
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1), 0 8px 16px rgba(0, 0, 0, 0.1);
}
```

### 4. Spread Radius

```css
.element {
  box-shadow: 0 0 0 4px rgba(0, 0, 0, 0.1);
  /* offset-x offset-y blur-radius spread-radius color */
}
```

## Text Shadows

Text shadows add depth to text elements.

### 1. Basic Text Shadow

```css
.text {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  /* offset-x offset-y blur-radius color */
}
```

### 2. Multiple Text Shadows

```css
.text {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3), -2px -2px 4px rgba(255, 255, 255, 0.3);
}
```

### 3. Glow Effect

```css
.text {
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
}
```

## CSS Filters

Filters apply visual effects to elements.

### 1. Basic Filters

```css
.element {
  filter: blur(5px);
  filter: brightness(150%);
  filter: contrast(200%);
  filter: grayscale(50%);
  filter: hue-rotate(90deg);
  filter: invert(100%);
  filter: opacity(50%);
  filter: saturate(200%);
  filter: sepia(50%);
}
```

### 2. Multiple Filters

```css
.element {
  filter: brightness(150%) contrast(120%) saturate(150%);
}
```

### 3. Filter Functions

```css
.element {
  /* Custom brightness */
  filter: brightness(1.5);

  /* Custom contrast */
  filter: contrast(1.2);

  /* Custom grayscale */
  filter: grayscale(0.5);

  /* Custom hue rotation */
  filter: hue-rotate(90deg);

  /* Custom invert */
  filter: invert(1);

  /* Custom opacity */
  filter: opacity(0.5);

  /* Custom saturation */
  filter: saturate(1.5);

  /* Custom sepia */
  filter: sepia(0.5);
}
```

## Common Use Cases

### 1. Card Design

```css
.card {
  background: white;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}

.card:hover {
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

### 2. Floating Elements

```css
.floating {
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  transform: translateY(-5px);
  transition: all 0.3s ease;
}

.floating:hover {
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
  transform: translateY(-10px);
}
```

### 3. Image Effects

```css
.image {
  transition: filter 0.3s ease;
}

.image:hover {
  filter: brightness(110%) contrast(120%) saturate(150%);
}
```

### 4. Text Effects

```css
.heading {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.glow-text {
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
}
```

## Performance Considerations

### 1. Shadow Performance

```css
/* Better performance */
.element {
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Worse performance */
.element {
  box-shadow: 0 0 20px 10px rgba(0, 0, 0, 0.1);
}
```

### 2. Filter Performance

```css
/* Better performance */
.element {
  filter: brightness(1.2);
}

/* Worse performance */
.element {
  filter: blur(10px) brightness(1.2) contrast(1.2) saturate(1.2);
}
```

## Best Practices

1. Use subtle shadows for depth
2. Combine shadows with transitions for interactive effects
3. Use filters sparingly to maintain performance
4. Consider mobile devices when using heavy effects
5. Test across different browsers for compatibility

## Next Steps

- Learn about [Media Queries](14-media-queries.md)
- Study [Responsive Images](15-responsive-images.md)
- Explore [Mobile-First Design](16-mobile-first.md)
