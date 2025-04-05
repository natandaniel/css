# CSS Frameworks and Libraries

CSS frameworks and libraries provide pre-built components and utilities to speed up development. This guide covers popular frameworks and how to use them effectively.

## Popular CSS Frameworks

### 1. Bootstrap

Bootstrap is one of the most popular CSS frameworks, providing a comprehensive set of components and utilities.

```html
<!-- Include Bootstrap CSS -->
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
/>

<!-- Basic Bootstrap components -->
<div class="container">
  <div class="row">
    <div class="col-md-6">
      <div class="card">
        <div class="card-header">Card Title</div>
        <div class="card-body">
          <h5 class="card-title">Special title treatment</h5>
          <p class="card-text">
            With supporting text below as a natural lead-in to additional
            content.
          </p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>
    <div class="col-md-6">
      <div class="alert alert-success" role="alert">
        This is a success alert!
      </div>
    </div>
  </div>
</div>
```

#### Customizing Bootstrap

```scss
// Custom variables
$primary: #3498db;
$secondary: #2ecc71;
$font-family-base: "Roboto", sans-serif;

// Import Bootstrap
@import "~bootstrap/scss/bootstrap";

// Custom styles
.custom-card {
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
```

### 2. Tailwind CSS

Tailwind CSS is a utility-first CSS framework that provides low-level utility classes.

```html
<!-- Include Tailwind CSS -->
<link
  href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css"
  rel="stylesheet"
/>

<!-- Using Tailwind utility classes -->
<div class="container mx-auto px-4">
  <div class="flex flex-wrap -mx-4">
    <div class="w-full md:w-1/2 px-4 mb-8">
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <div class="bg-gray-100 px-6 py-4 border-b border-gray-200">
          <h3 class="text-lg font-semibold text-gray-800">Card Title</h3>
        </div>
        <div class="p-6">
          <h5 class="text-xl font-bold mb-2">Special title treatment</h5>
          <p class="text-gray-600 mb-4">
            With supporting text below as a natural lead-in to additional
            content.
          </p>
          <a
            href="#"
            class="inline-block bg-blue-500 hover:bg-blue-600 text-white font-medium py-2 px-4 rounded"
            >Go somewhere</a
          >
        </div>
      </div>
    </div>
    <div class="w-full md:w-1/2 px-4 mb-8">
      <div
        class="bg-green-100 border-l-4 border-green-500 text-green-700 p-4 rounded"
      >
        <p class="font-bold">Success!</p>
        <p>This is a success alert!</p>
      </div>
    </div>
  </div>
</div>
```

#### Customizing Tailwind

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: "#3498db",
        secondary: "#2ecc71",
      },
      fontFamily: {
        sans: ["Roboto", "sans-serif"],
      },
    },
  },
  plugins: [],
};
```

### 3. Foundation

Foundation is a responsive front-end framework with a focus on flexibility.

```html
<!-- Include Foundation CSS -->
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/foundation-sites@6.7.5/dist/css/foundation.min.css"
/>

<!-- Basic Foundation components -->
<div class="grid-container">
  <div class="grid-x grid-padding-x">
    <div class="cell medium-6">
      <div class="card">
        <div class="card-section">
          <h4>Card Title</h4>
          <p>
            With supporting text below as a natural lead-in to additional
            content.
          </p>
          <a href="#" class="button primary">Go somewhere</a>
        </div>
      </div>
    </div>
    <div class="cell medium-6">
      <div class="callout success">
        <h5>Success!</h5>
        <p>This is a success alert!</p>
      </div>
    </div>
  </div>
</div>
```

#### Customizing Foundation

```scss
// Custom Foundation settings
$primary-color: #3498db;
$secondary-color: #2ecc71;
$body-font-family: "Roboto", sans-serif;

// Import Foundation
@import "~foundation-sites/scss/foundation";

// Include all Foundation components
@include foundation-everything;

// Custom styles
.custom-card {
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
```

### 4. Bulma

Bulma is a modern CSS framework based on Flexbox.

```html
<!-- Include Bulma CSS -->
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css"
/>

<!-- Basic Bulma components -->
<div class="container">
  <div class="columns">
    <div class="column is-half">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">Card Title</p>
        </header>
        <div class="card-content">
          <div class="content">
            <h4>Special title treatment</h4>
            <p>
              With supporting text below as a natural lead-in to additional
              content.
            </p>
            <a class="button is-primary">Go somewhere</a>
          </div>
        </div>
      </div>
    </div>
    <div class="column is-half">
      <div class="notification is-success">
        <button class="delete"></button>
        <strong>Success!</strong> This is a success alert!
      </div>
    </div>
  </div>
</div>
```

#### Customizing Bulma

```scss
// Custom Bulma variables
$primary: #3498db;
$info: #2ecc71;
$family-sans-serif: "Roboto", sans-serif;

// Import Bulma
@import "~bulma/bulma";

// Custom styles
.custom-card {
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
```

## CSS Libraries

### 1. Animate.css

Animate.css provides a collection of pre-built animations.

```html
<!-- Include Animate.css -->
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
/>

<!-- Using Animate.css classes -->
<div class="animate__animated animate__fadeIn">
  <h1>This text will fade in</h1>
</div>

<div class="animate__animated animate__bounce animate__delay-1s">
  <p>This will bounce after a 1-second delay</p>
</div>

<div class="animate__animated animate__pulse animate__infinite">
  <button>This button will pulse infinitely</button>
</div>
```

### 2. Font Awesome

Font Awesome provides a comprehensive icon library.

```html
<!-- Include Font Awesome -->
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css"
/>

<!-- Using Font Awesome icons -->
<button class="btn"><i class="fas fa-home"></i> Home</button>
<button class="btn"><i class="fas fa-user"></i> Profile</button>
<button class="btn"><i class="fas fa-cog"></i> Settings</button>

<!-- Icon sizes -->
<i class="fas fa-star fa-lg"></i>
<i class="fas fa-star fa-2x"></i>
<i class="fas fa-star fa-3x"></i>

<!-- Icon animations -->
<i class="fas fa-spinner fa-spin"></i>
<i class="fas fa-circle-notch fa-spin"></i>
```

### 3. Material Icons

Material Icons provides Google's Material Design icons.

```html
<!-- Include Material Icons -->
<link
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
  rel="stylesheet"
/>

<!-- Using Material Icons -->
<button class="btn"><span class="material-icons">home</span> Home</button>
<button class="btn"><span class="material-icons">person</span> Profile</button>
<button class="btn">
  <span class="material-icons">settings</span> Settings
</button>

<!-- Icon sizes -->
<span class="material-icons md-18">star</span>
<span class="material-icons md-24">star</span>
<span class="material-icons md-36">star</span>
<span class="material-icons md-48">star</span>
```

## Choosing a Framework

### 1. Project Requirements

Consider these factors when choosing a framework:

- **Project Size**: For small projects, a lightweight framework like Bulma might be better than a comprehensive one like Bootstrap.
- **Design Requirements**: If you need a specific design system, choose a framework that aligns with it.
- **Browser Support**: Ensure the framework supports your target browsers.
- **Performance**: Consider the file size and performance impact.
- **Learning Curve**: Evaluate the time needed to learn the framework.

### 2. Framework Comparison

| Framework  | Pros                                                 | Cons                                           |
| ---------- | ---------------------------------------------------- | ---------------------------------------------- |
| Bootstrap  | Comprehensive, widely used, extensive documentation  | Can be bloated, generic look if not customized |
| Tailwind   | Highly customizable, small bundle size with PurgeCSS | Steep learning curve, verbose HTML             |
| Foundation | Flexible, semantic markup                            | Less popular, steeper learning curve           |
| Bulma      | Modern, based on Flexbox, lightweight                | Smaller ecosystem, fewer components            |

## Integration with Build Tools

### 1. Using npm

```bash
# Install Bootstrap
npm install bootstrap

# Install Tailwind CSS
npm install tailwindcss

# Install Foundation
npm install foundation-sites

# Install Bulma
npm install bulma
```

### 2. Webpack Configuration

```javascript
// webpack.config.js
const path = require("path");

module.exports = {
  entry: "./src/index.js",
  output: {
    filename: "bundle.js",
    path: path.resolve(__dirname, "dist"),
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ["style-loader", "css-loader", "postcss-loader"],
      },
      {
        test: /\.scss$/,
        use: ["style-loader", "css-loader", "sass-loader"],
      },
    ],
  },
};
```

### 3. PostCSS Configuration (for Tailwind)

```javascript
// postcss.config.js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

## Best Practices

1. Choose a framework that aligns with your project requirements
2. Customize the framework to match your design system
3. Use only the components you need to reduce file size
4. Consider using a CSS-in-JS solution for component-based architectures
5. Implement proper responsive design using framework utilities
6. Use framework-specific tools for optimization
7. Keep frameworks and libraries updated for security and features
8. Document customizations and extensions
9. Test across different browsers and devices
10. Consider accessibility when using framework components

## Next Steps

- Learn about [Advanced CSS Techniques](21-advanced-techniques.md)
- Study [CSS Architecture](22-architecture.md)
- Explore [CSS-in-JS Solutions](23-css-in-js.md)
