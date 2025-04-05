# Responsive Images

Responsive images ensure that images look great across all devices while optimizing performance.

## Basic Responsive Images

### 1. Fluid Images

```css
.responsive-image {
  max-width: 100%;
  height: auto;
}
```

### 2. Aspect Ratio Preservation

```css
.image-container {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%; /* 16:9 Aspect Ratio */
}

.image-container img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

## HTML Solutions

### 1. srcset Attribute

```html
<img
  src="image-small.jpg"
  srcset="image-small.jpg 300w, image-medium.jpg 600w, image-large.jpg 900w"
  sizes="(max-width: 600px) 300px,
            (max-width: 900px) 600px,
            900px"
  alt="Responsive image"
/>
```

### 2. picture Element

```html
<picture>
  <source media="(min-width: 800px)" srcset="large.jpg" />
  <source media="(min-width: 400px)" srcset="medium.jpg" />
  <img src="small.jpg" alt="Responsive image" />
</picture>
```

### 3. Art Direction

```html
<picture>
  <source media="(min-width: 800px)" srcset="landscape.jpg" />
  <source media="(max-width: 799px)" srcset="portrait.jpg" />
  <img src="fallback.jpg" alt="Art directed image" />
</picture>
```

## CSS Solutions

### 1. Object Fit

```css
.image {
  width: 100%;
  height: 300px;
  object-fit: cover; /* cover, contain, fill, none, scale-down */
  object-position: center;
}
```

### 2. Background Images

```css
.hero {
  background-image: url("small.jpg");
  background-size: cover;
  background-position: center;
  height: 300px;
}

@media (min-width: 768px) {
  .hero {
    background-image: url("large.jpg");
  }
}
```

### 3. CSS Grid Images

```css
.image-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.image-grid img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

## Performance Optimization

### 1. Lazy Loading

```html
<img src="image.jpg" loading="lazy" alt="Lazy loaded image" />
```

### 2. Blur-up Technique

```css
.image-container {
  position: relative;
  background-color: #f0f0f0;
}

.image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 0.3s;
}

.image.loaded {
  opacity: 1;
}
```

### 3. Progressive Loading

```css
.progressive-image {
  filter: blur(10px);
  transition: filter 0.3s;
}

.progressive-image.loaded {
  filter: blur(0);
}
```

## Common Use Cases

### 1. Hero Images

```css
.hero {
  position: relative;
  height: 50vh;
  min-height: 300px;
  max-height: 600px;
}

.hero img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}
```

### 2. Gallery Images

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
}

.gallery img {
  width: 100%;
  aspect-ratio: 1;
  object-fit: cover;
  transition: transform 0.3s;
}

.gallery img:hover {
  transform: scale(1.05);
}
```

### 3. Product Images

```css
.product-image {
  width: 100%;
  max-width: 500px;
  aspect-ratio: 1;
  object-fit: contain;
  background: white;
}
```

## Best Practices

1. Always provide alt text for accessibility
2. Use appropriate image formats (WebP with fallbacks)
3. Implement lazy loading for better performance
4. Consider using a CDN for image delivery
5. Optimize images before deployment
6. Use appropriate image sizes for different devices
7. Implement proper error handling for failed image loads

## Next Steps

- Learn about [Mobile-First Design](16-mobile-first.md)
- Study [CSS Organization](17-organization.md)
- Explore [Performance Optimization](18-performance.md)
