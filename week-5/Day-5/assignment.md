# Assignment:  Webpack Practice

## Objective

Solidify your understanding of Webpack and Babel by creating a Next.js project that demonstrates key concepts learned throughout the week. This project should reflect your ability to set up, configure, and optimize a web application using these tools.

## Instructions

### Part 1: Setup a Next.js Project

1. **Initialize a New Next.js Application**:

   - Use `create-next-app` to bootstrap a new Next.js project.
   - Name your project `webpack-babel-nextjs-review`.

2. **Project Structure**:
   - Organize your application code within the `/src` directory. Structure your Next.js pages under `/src/app` and create a shared layout component in `/src/components`.

### Part 2: Explore Webpack Features in Next.js

1. **Custom Webpack Configuration**:

   - Extend the default Next.js Webpack configuration to include a custom Babel loader for processing a specific type of file (e.g., Markdown or SVG files).
   - Document the steps in your `README.md`.

2. **Optimization Techniques**:
   - Implement lazy loading for a heavy component using Next.js dynamic imports.
   - Configure the `splitChunks` option in `next.config.js` to optimize bundle sizes.

### Part 3: Implement Key Babel Features

1. **Babel Configuration**:

   - Create a custom `.babelrc` or `babel.config.json` in your project to utilize the `@babel/preset-env` and at least one other Babel plugin or preset of your choice.
   - Explain your choice of Babel plugin or preset in your `README.md`.

2. **Transpilation Demonstration**:
   - Write ES6+ JavaScript features (e.g., arrow functions, async/await) in your Next.js project. Demonstrate how Babel transpiles these features for compatibility.
