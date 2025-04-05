# CSS Syntax and Selectors

CSS selectors are patterns used to select and style HTML elements. Understanding selectors is crucial for effective CSS styling.

## Basic Selectors

### 1. Element Selector

```css
p {
  color: blue;
}
```

### 2. Class Selector

```css
.highlight {
  background-color: yellow;
}
```

### 3. ID Selector

```css
#header {
  font-size: 24px;
}
```

### 4. Universal Selector

```css
* {
  margin: 0;
  padding: 0;
}
```

## Combinators

### 1. Descendant Selector (space)

```css
div p {
  color: red;
}
```

### 2. Child Selector (>)

```css
div > p {
  color: red;
}
```

### 3. Adjacent Sibling Selector (+)

```css
h2 + p {
  color: red;
}
```

### 4. General Sibling Selector (~)

```css
h2 ~ p {
  color: red;
}
```

## Attribute Selectors

### 1. Basic Attribute

```css
[type="text"] {
  border: 1px solid gray;
}
```

### 2. Attribute Contains

```css
[class*="btn"] {
  padding: 10px;
}
```

### 3. Attribute Starts With

```css
[class^="btn-"] {
  margin: 5px;
}
```

### 4. Attribute Ends With

```css
[href$=".pdf"] {
  color: red;
}
```

## Pseudo-classes

### 1. State-based

```css
a:hover {
  color: red;
}

input:focus {
  border-color: blue;
}
```

### 2. Position-based

```css
li:first-child {
  font-weight: bold;
}

li:last-child {
  border-bottom: none;
}
```

### 3. Form-based

```css
input:required {
  border-color: red;
}

input:disabled {
  background-color: gray;
}
```

## Pseudo-elements

### 1. Content

```css
p::before {
  content: "→ ";
}

p::after {
  content: " ←";
}
```

### 2. Text Selection

```css
::selection {
  background-color: yellow;
  color: black;
}
```

## Specificity

CSS specificity determines which styles are applied when multiple rules target the same element:

1. Inline styles (1000)
2. IDs (100)
3. Classes, attributes, and pseudo-classes (10)
4. Elements and pseudo-elements (1)

Example:

```css
#header .nav li {
  /* 111 */
}
.nav li {
  /* 11 */
}
li {
  /* 1 */
}
```

## Best Practices

1. Use classes for reusable styles
2. Avoid overly specific selectors
3. Minimize use of IDs for styling
4. Use meaningful class names
5. Keep selectors as simple as possible

## Next Steps

- Learn about the [Box Model](03-box-model.md)
- Explore [Colors and Backgrounds](04-colors-backgrounds.md)
- Study [Display Properties](05-display-properties.md)
