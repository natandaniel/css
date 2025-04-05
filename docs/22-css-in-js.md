# CSS-in-JS

CSS-in-JS is a styling approach that allows you to write CSS directly within JavaScript code. This technique has gained popularity with modern JavaScript frameworks and component-based architectures.

## What is CSS-in-JS?

CSS-in-JS is a pattern where CSS is composed using JavaScript instead of being defined in separate files. This approach:

- Scopes styles to components
- Enables dynamic styling based on props
- Provides runtime style generation
- Supports theme customization
- Eliminates CSS naming conflicts

## Popular Libraries

### 1. Styled Components

```javascript
import styled from 'styled-components';

const Button = styled.button`
  background-color: ${props => props.primary ? 'blue' : 'gray'};
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;

  &:hover {
    opacity: 0.9;
  }
`;

// Usage
<Button primary>Primary Button</Button>
<Button>Secondary Button</Button>
```

### 2. Emotion

```javascript
import { css } from "@emotion/react";

const buttonStyles = css`
  background-color: blue;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;

  &:hover {
    opacity: 0.9;
  }
`;

// Usage
<button css={buttonStyles}>Click Me</button>;
```

### 3. JSS

```javascript
import { createUseStyles } from "react-jss";

const useStyles = createUseStyles({
  button: {
    backgroundColor: "blue",
    color: "white",
    padding: "10px 20px",
    border: "none",
    borderRadius: "4px",
    "&:hover": {
      opacity: 0.9,
    },
  },
});

// Usage
function Button() {
  const classes = useStyles();
  return <button className={classes.button}>Click Me</button>;
}
```

## Key Features

### 1. Dynamic Styling

```javascript
const DynamicButton = styled.button`
  background-color: ${(props) =>
    props.variant === "primary" ? "blue" : "gray"};
  font-size: ${(props) => (props.size === "large" ? "18px" : "16px")};
  padding: ${(props) => (props.size === "large" ? "15px 30px" : "10px 20px")};
`;

// Usage
<DynamicButton variant="primary" size="large">
  Large Primary Button
</DynamicButton>;
```

### 2. Theme Support

```javascript
// Theme definition
const theme = {
  colors: {
    primary: "blue",
    secondary: "gray",
    text: "black",
  },
  spacing: {
    small: "8px",
    medium: "16px",
    large: "24px",
  },
};

// Theme provider
import { ThemeProvider } from "styled-components";

function App() {
  return (
    <ThemeProvider theme={theme}>
      <YourApp />
    </ThemeProvider>
  );
}

// Themed component
const ThemedButton = styled.button`
  background-color: ${(props) => props.theme.colors.primary};
  padding: ${(props) => props.theme.spacing.medium};
  color: white;
`;
```

### 3. Global Styles

```javascript
import { createGlobalStyle } from "styled-components";

const GlobalStyle = createGlobalStyle`
  body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
  }
  
  * {
    box-sizing: border-box;
  }
`;

// Usage
function App() {
  return (
    <>
      <GlobalStyle />
      <YourApp />
    </>
  );
}
```

### 4. CSS Animations

```javascript
import { keyframes } from "styled-components";

const fadeIn = keyframes`
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
`;

const AnimatedElement = styled.div`
  animation: ${fadeIn} 0.5s ease-in-out;
`;
```

## Performance Considerations

### 1. Server-Side Rendering

```javascript
// With styled-components
import { ServerStyleSheet } from "styled-components";

function renderWithStyles(html) {
  const sheet = new ServerStyleSheet();
  try {
    const styledHtml = sheet.collectStyles(html);
    const styleTags = sheet.getStyleElement();
    return { styledHtml, styleTags };
  } finally {
    sheet.seal();
  }
}
```

### 2. Code Splitting

```javascript
// Dynamic imports for styles
const DynamicStyles = React.lazy(() => import("./DynamicStyles"));

function App() {
  return (
    <Suspense fallback={<div>Loading styles...</div>}>
      <DynamicStyles />
    </Suspense>
  );
}
```

### 3. Style Caching

```javascript
// With emotion
import { CacheProvider } from "@emotion/react";
import createCache from "@emotion/cache";

const cache = createCache({
  key: "my-app",
  prepend: true, // Ensures styles are injected first
});

function App() {
  return (
    <CacheProvider value={cache}>
      <YourApp />
    </CacheProvider>
  );
}
```

## Best Practices

1. **Component Scoping**: Keep styles close to components
2. **Reusable Styles**: Create shared style components
3. **Theme Consistency**: Use theme objects for design tokens
4. **Performance**: Implement proper SSR and code splitting
5. **Maintainability**: Use consistent naming and organization
6. **Testing**: Test styled components with snapshot testing
7. **Accessibility**: Ensure styles don't break accessibility
8. **Responsive Design**: Use media queries within components

## Common Patterns

### 1. Style Composition

```javascript
const baseButtonStyles = css`
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
`;

const PrimaryButton = styled.button`
  ${baseButtonStyles}
  background-color: blue;
  color: white;
`;

const SecondaryButton = styled.button`
  ${baseButtonStyles}
  background-color: gray;
  color: white;
`;
```

### 2. Style Props

```javascript
const Button = styled.button`
  ${(props) =>
    props.fullWidth &&
    css`
      width: 100%;
    `}

  ${(props) =>
    props.disabled &&
    css`
      opacity: 0.5;
      cursor: not-allowed;
    `}
`;

// Usage
<Button fullWidth disabled>
  Full Width Disabled Button
</Button>;
```

### 3. Style Mixins

```javascript
const flexCenter = css`
  display: flex;
  justify-content: center;
  align-items: center;
`;

const Card = styled.div`
  ${flexCenter}
  flex-direction: column;
  padding: 20px;
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
`;
```

## Drawbacks and Considerations

1. **Runtime Overhead**: Styles are generated at runtime
2. **Bundle Size**: Additional JavaScript for style processing
3. **Learning Curve**: New syntax and patterns to learn
4. **Tooling**: Requires specific build tools and configurations
5. **Debugging**: Can be more challenging than traditional CSS
6. **SSR Complexity**: Requires additional setup for server rendering

## When to Use CSS-in-JS

- Component-based architectures
- Applications requiring dynamic theming
- Projects with complex style logic
- Teams working with JavaScript-heavy codebases
- Applications needing style isolation

## When to Avoid CSS-in-JS

- Simple static websites
- Projects with strict performance requirements
- Teams more comfortable with traditional CSS
- Applications with minimal styling needs
- Projects with limited JavaScript usage
