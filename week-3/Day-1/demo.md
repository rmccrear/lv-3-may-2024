# Week 3, Day 1, Hour 1: Review of Sass and 7-1 Architecture in Next.js

Kicking off our journey into advanced styling with Next.js, let's start with a refresher on Sass (Syntactically Awesome Style Sheets) and specifically dive into the 7-1 architecture pattern. This architecture facilitates a modular and scalable approach to managing styles in your projects.

## Quick Review of Sass

Sass is a preprocessor that adds power and elegance to the basic CSS language. It allows you to use variables, nested rules, mixins, functions, and more, all within a well-organized framework.

## Understanding the 7-1 Architecture Pattern

The 7-1 architecture pattern divides your Sass files into seven folders, plus one main file to import all other files into your project. Here's a quick breakdown:

- **Base/**: Contains global styles, such as resets.
- **Components/**: For each UI component.
- **Layout/**: Contains styling for larger layout components (e.g., header, footer).
- **Pages/**: Page-specific styling.
- **Themes/**: Different themes for your application.
- **Abstracts/**: Holds Sass tools, helpers, variables, and mixins.
- **Vendors/**: For all third-party CSS.

### Single Import in Next.js

In a Next.js project, you can integrate the 7-1 pattern by creating a `styles/` directory at the root. Inside, structure your Sass files following the 7-1 pattern, then import your main Sass file (`styles.scss`) into your Next.js project, typically in `layout.js` for global scope.

```jsx
// In _app.js or _app.tsx
import '../styles/styles.scss';
```

Ensure you have `sass` installed in your Next.js project:

```bash
npm install --save-dev sass
```

## Best Practices for Organizing Styles

- **Modularity**: Keep your styles modular by separating them into logical files and folders. This makes it easier to maintain and update your styles.
- **Consistency**: Use consistent naming conventions across your Sass files to make it easier to understand and manage your styles.
- **Global Variables**: Utilize Sass variables for theme colors, fonts, and other constants to ensure consistency and ease of changes.

### Example Directory Structure

Here's how your `styles/` directory might look following the 7-1 pattern:

```
styles/
|
|-- abstracts/
|   |-- _variables.scss    // Sass Variables
|   |-- _mixins.scss       // Sass Mixins
|
|-- base/
|   |-- _reset.scss        // Reset/Normalize
|   |-- _typography.scss   // Typography rules
|
|-- components/
|   |-- _buttons.scss      // Buttons
|   |-- _carousel.scss     // Carousel
|
|-- layout/
|   |-- _header.scss       // Header
|   |-- _footer.scss       // Footer
|   |-- _grid.scss         // Grid system
|
|-- pages/
|   |-- _home.scss         // Home specific styles
|   |-- _about.scss        // About specific styles
|
|-- themes/
|   |-- _theme.scss        // Default theme
|
|-- vendors/
|   |-- _bootstrap.scss    // Bootstrap overrides
|
`-- styles.scss            // Main Sass file importing all above
```

In `styles.scss`, you'd import each Sass partial:

```scss
// styles.scss
@import 'abstracts/variables';
@import 'abstracts/mixins';

@import 'base/reset';
@import 'base/typography';

// Continue importing other files
```

This setup provides a robust foundation for styling your Next.js application, leveraging the power of Sass within a structured, maintainable architecture.

<!--! Hour 2  -->

# Week 3, Day 1, Hour 2: Implementing SCSS Modules and BEM in Next.js

In this hour, we dive deeper into the integration of SCSS Modules in Next.js, highlighting the BEM (Block Element Modifier) methodology and how it complements Next.js's modular design. Additionally, we'll touch upon using `className` and the conversion of some HTML attributes from hyphenated to camelCase in JSX.

## SCSS Modules in Next.js

SCSS Modules provide a way to include component-level styles in your Next.js application, ensuring that styles are locally scoped by default. This means that styles defined in a module are not leaked into other parts of your application, aligning perfectly with the component-based architecture of React and Next.js.

### Why BEM with SCSS Modules?

BEM stands for Block, Element, Modifier. It's a naming convention that makes your CSS more readable and understandable. With SCSS Modules, each React component can be treated as a "Block," making it easier to manage and understand your component's styling. This approach minimizes conflicts and enhances reusability.

### Creating a SCSS Module

To create a SCSS module for a component:

1. Create a new file named `ComponentName.module.scss`.
2. Define your styles using BEM conventions within this file.

```scss
// Button.module.scss
.button {
  &__primary {
    background-color: blue;
    color: white;
  }

  &__disabled {
    background-color: grey;
    color: darkgray;
  }
}
```

### Using SCSS Modules in Components

Import your `.module.scss` file into your component and use the styles with `className`.

```jsx
import React from 'react';
import styles from './Button.module.scss';

function Button({ primary, disabled, children }) {
  const buttonClass = `
    ${styles.button}
    ${primary ? styles.button__primary : ''}
    ${disabled ? styles.button__disabled : ''}
  `;

  return (
    <button className={buttonClass} disabled={disabled}>
      {children}
    </button>
  );
}
```

This setup allows you to keep your CSS modular and scoped to each component, following the BEM methodology within the context of Next.js's component-based structure.

## Understanding `className` and JSX Attribute Naming

In React and Next.js, `className` is used instead of the `class` attribute in HTML to apply CSS classes. This change is due to `class` being a reserved word in JavaScript. Similarly, attributes that typically include hyphens in HTML are written in camelCase in JSX.

### Examples of Attribute Conversion

- `class` becomes `className`
- `onclick` becomes `onClick`
- `data-test-id` becomes `dataTestId`

Here's how you might use these in a component:

```jsx
<div className="container">
  <button onClick={handleClick} dataTestId="uniqueId">
    Click Me
  </button>
</div>
```

This naming convention aligns with JavaScript's camelCase naming, ensuring consistency across your JSX code.

<!--* Show deployment steps to Netlify  -->

## Conclusion

Integrating SCSS Modules with the BEM methodology in Next.js projects promotes a modular, scalable approach to styling. By understanding how to effectively use `className` and adapting to JSX's camelCase attributes, you can further refine your components for clarity, reusability, and maintainability. This hour sets the stage for more advanced styling practices and prepares you to tackle dynamic UI challenges with confidence.
