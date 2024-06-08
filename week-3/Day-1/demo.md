# Week 3, Day 1: Introduction to Webpack

Welcome to Day 1 of Week 3! Today, we will introduce Webpack, set up a project, and demonstrate JavaScript file bundling.

## Objectives

- Understand the purpose and benefits of using Webpack.
- Set up a basic Webpack project.
- Demonstrate how to bundle JavaScript files using Webpack.

## Instructor Notes

### Introduction to Webpack

- Explain what Webpack is and why it is used in modern web development.
  - Webpack is a module bundler that allows you to bundle JavaScript files and other assets for usage in a browser.
  - Benefits include modular development, efficient bundling, and support for various asset types.

### Setting Up a Webpack Project

- Guide students through setting up a basic Webpack project from scratch.

### Demonstrating JavaScript File Bundling

- Show how Webpack can bundle multiple JavaScript files into a single file.

## Hourly Breakdown

### Hour 1: Introduction to Webpack

- **Objectives**:
  - Understand the purpose and benefits of using Webpack.
- **Teaching Ideas**:
  - Explain Webpack:
    - Webpack is a static module bundler for modern JavaScript applications.
    - It builds a dependency graph, mapping every module your project needs and bundling them into one or more bundles.
  - Benefits of using Webpack:
    - Efficient module bundling.
    - Support for JavaScript and non-JavaScript files.
    - Code splitting for better performance.

### Hour 2: Setting Up a Basic Webpack Project

- **Objectives**:
  - Set up a basic Webpack project.
- **Teaching Ideas**:

  - Create a new project directory:

    ```bash
    mkdir webpack-demo
    cd webpack-demo
    ```

  - Initialize a new npm project:

    ```bash
    npm init -y
    ```

  - Install Webpack and Webpack CLI as development dependencies:

    ```bash
    npm install --save-dev webpack webpack-cli
    ```

  - Create the following project structure:

    ```
    webpack-demo/
    ├── dist/
    ├── src/
    │   └── index.js
    ├── package.json
    └── webpack.config.js
    ```

  - Create a basic `webpack.config.js` file:

    ```js
    const path = require('path');

    module.exports = {
      entry: './src/index.js',
      output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist'),
      },
    };
    ```

- **Objectives**:
  - Demonstrate how to bundle JavaScript files using Webpack.
- **Teaching Ideas**:

  - Create a simple `index.js` file in the `src` directory:

    ```js
    function component() {
      const element = document.createElement('div');
      element.innerHTML = 'Hello, Webpack!';
      return element;
    }

    document.body.appendChild(component());
    ```

  - Add a script to `package.json` to run Webpack:

    ```json
    "scripts": {
        "build": "webpack"
    }
    ```

  - Run Webpack to create the bundle:

    ```bash
    npm run build
    ```

  - Explain the output in the `dist` directory:
    - The bundled file (`bundle.js`) contains the code from `src/index.js`.

### Practical Exercise

- Have students follow along and set up their own Webpack project.
- Assist students in running Webpack to bundle their JavaScript files.
- Encourage students to modify their `index.js` file and observe the changes in the bundled output.

## Code Snippets

```bash
# Create project directory and initialize npm
mkdir webpack-demo
cd webpack-demo
npm init -y

# Install Webpack and Webpack CLI
npm install --save-dev webpack webpack-cli
```

```js
// webpack.config.js
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
};
```

```js
// src/index.js
function component() {
  const element = document.createElement('div');
  element.innerHTML = 'Hello, Webpack!';
  return element;
}

document.body.appendChild(component());
```

```json
// Add build script to package.json
"scripts": {
    "build": "webpack"
}
```

```bash
# Run Webpack to create the bundle
npm run build
```

## Conclusion

- Summarize the key points covered:
  - Webpack is a powerful tool for bundling JavaScript and other assets.
  - Setting up a basic Webpack project involves configuring an entry point and output.
  - Webpack can efficiently bundle multiple JavaScript files into a single file.
- Encourage students to explore more advanced Webpack features in their own time.
