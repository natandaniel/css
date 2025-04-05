# Transitions and Animations

CSS transitions and animations allow you to create smooth, interactive effects that enhance user experience.

## Transitions

Transitions provide a way to control animation speed when changing CSS properties.

### 1. Basic Transition

```css
.element {
  transition: background-color 0.3s ease;
}
```

### 2. Transition Properties

```css
.element {
  /* Individual properties */
  transition-property: background-color, color;
  transition-duration: 0.3s;
  transition-timing-function: ease;
  transition-delay: 0.1s;

  /* Shorthand */
  transition: background-color 0.3s ease 0.1s;
}
```

### 3. Timing Functions

```css
.element {
  transition-timing-function: ease; /* Default */
  transition-timing-function: linear; /* Constant speed */
  transition-timing-function: ease-in; /* Slow start */
  transition-timing-function: ease-out; /* Slow end */
  transition-timing-function: ease-in-out; /* Slow start and end */
  transition-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1); /* Custom */
}
```

### 4. Multiple Transitions

```css
.element {
  transition: background-color 0.3s ease, color 0.5s linear,
    transform 0.2s ease-in-out;
}
```

## Animations

Animations allow you to create more complex, multi-step animations.

### 1. Keyframes

```css
@keyframes slide-in {
  0% {
    transform: translateX(-100%);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}
```

### 2. Animation Properties

```css
.element {
  /* Individual properties */
  animation-name: slide-in;
  animation-duration: 1s;
  animation-timing-function: ease;
  animation-delay: 0.2s;
  animation-iteration-count: 1;
  animation-direction: normal;
  animation-fill-mode: forwards;
  animation-play-state: running;

  /* Shorthand */
  animation: slide-in 1s ease 0.2s 1 normal forwards running;
}
```

### 3. Animation Iteration

```css
.element {
  animation-iteration-count: 1; /* Default */
  animation-iteration-count: infinite; /* Repeat forever */
  animation-iteration-count: 3; /* Repeat 3 times */
}
```

### 4. Animation Direction

```css
.element {
  animation-direction: normal; /* Default */
  animation-direction: reverse; /* Play backwards */
  animation-direction: alternate; /* Alternate forwards and backwards */
  animation-direction: alternate-reverse; /* Start backwards then alternate */
}
```

### 5. Animation Fill Mode

```css
.element {
  animation-fill-mode: none; /* Default */
  animation-fill-mode: forwards; /* Retain final keyframe */
  animation-fill-mode: backwards; /* Apply first keyframe during delay */
  animation-fill-mode: both; /* Apply both forwards and backwards */
}
```

## Common Use Cases

### 1. Hover Effects

```css
.button {
  background-color: blue;
  transition: background-color 0.3s ease;
}

.button:hover {
  background-color: darkblue;
}
```

### 2. Fade In

```css
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.element {
  animation: fade-in 0.5s ease forwards;
}
```

### 3. Slide In

```css
@keyframes slide-in {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}

.element {
  animation: slide-in 0.5s ease forwards;
}
```

### 4. Pulse

```css
@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}

.element {
  animation: pulse 1s ease infinite;
}
```

## Performance Considerations

### 1. GPU Acceleration

```css
.element {
  /* Properties that trigger GPU acceleration */
  transform: translateZ(0);
  will-change: transform;
}
```

### 2. Animation Performance

```css
.element {
  /* Avoid animating these properties */
  /* width, height, margin, padding, font-size */

  /* Prefer these properties */
  /* transform, opacity */
}
```

## Best Practices

1. Keep animations short and subtle
2. Use appropriate timing functions
3. Avoid animating layout-triggering properties
4. Consider reduced motion preferences
5. Test animations on different devices

## Next Steps

- Learn about [Transforms](12-transforms.md)
- Study [Shadows and Filters](13-shadows-filters.md)
- Explore [Media Queries](14-media-queries.md)
