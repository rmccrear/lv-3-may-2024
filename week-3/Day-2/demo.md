# Week 3, Day 2: Introduction to Babel

Welcome to Day 2 of Week 3! Today, we will introduce Babel, set it up in a project with Webpack, and demonstrate JavaScript transpilation.

## Objectives

- Understand the purpose and benefits of using Babel.
- Set up Babel in a Webpack project.
- Demonstrate how Babel transpiles modern JavaScript to ensure compatibility with older browsers.

## Instructor Notes

### Introduction to Babel

- Explain what Babel is and why it is used in modern web development.
  - Babel is a JavaScript compiler that allows you to use next-generation JavaScript, today.
  - It transpiles modern JavaScript (ES6+) to ES5 to ensure compatibility with older browsers.

### Setting Up Babel in a Webpack Project

- Guide students through adding Babel to an existing Webpack project and configuring it to transpile JavaScript files.

### Demonstrating JavaScript Transpilation

- Show how Babel can transpile modern JavaScript features into a form that is compatible with older browsers.

## Hourly Breakdown

### Hour 1: Introduction to Babel

- **Objectives**:
  - Understand the purpose and benefits of using Babel.
- **Teaching Ideas**:
  - Explain Babel:
    - Babel is a tool that helps developers write code using the latest JavaScript features, ensuring compatibility across all browsers.
  - Benefits of using Babel:
    - Enables the use of modern JavaScript syntax.
    - Helps avoid compatibility issues with older browsers.

### Hour 2: Setting Up Babel in a Webpack Project

- **Objectives**:
  - Set up Babel in a Webpack project.
- **Teaching Ideas**:

  - Install Babel and necessary presets:
    ```bash
    npm install --save-dev babel-loader @babel/core @babel/preset-env
    ```
  - Update `webpack.config.js` to use Babel loader:

    ```js
    const path = require('path');

    module.exports = {
      entry: './src/index.js',
      output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist'),
      },
      module: {
        rules: [
          {
            test: /\.js$/,
            exclude: /node_modules/,
            use: {
              loader: 'babel-loader',
              options: {
                presets: ['@babel/preset-env'],
              },
            },
          },
        ],
      },
    };
    ```

  - Create a Babel configuration file (`.babelrc`):

    ```json
    {
      "presets": ["@babel/preset-env"]
    }
    ```

- **Objectives**:
  - Demonstrate how Babel transpiles modern JavaScript.
- **Teaching Ideas**:

  - Modify `src/index.js` to include modern JavaScript syntax:

    ```js
    const arrowFunction = () => {
      console.log('Hello, Babel!');
    };

    arrowFunction();
    ```

  - Run Webpack to transpile the code:

    ```bash
    npm run build
    ```

  - Explain the transpiled output in `dist/bundle.js` and how Babel converts modern JavaScript features to ES5:

    ```js
    var arrowFunction = function arrowFunction() {
      console.log('Hello, Babel!');
    };

    arrowFunction();
    ```

### Practical Exercise

- Have students follow along and set up Babel in their own Webpack projects.
- Assist students in running Webpack to transpile their JavaScript files.
- Encourage students to try out different modern JavaScript features and observe how Babel transpiles them.

## Code Snippets

```bash
# Install Babel and necessary presets
npm install --save-dev babel-loader @babel/core @babel/preset-env
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
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader',
          options: {
            presets: ['@babel/preset-env'],
          },
        },
      },
    ],
  },
};
```

```json
// .babelrc
{
  "presets": ["@babel/preset-env"]
}
```

```js
// src/index.js
const arrowFunction = () => {
  console.log('Hello, Babel!');
};

arrowFunction();
```

```bash
# Run Webpack to create the bundle
npm run build
```

```js
// Transpiled output in dist/bundle.js
var arrowFunction = function arrowFunction() {
  console.log('Hello, Babel!');
};

arrowFunction();
```

## Conclusion

- Summarize the key points covered:
  - Babel is a powerful tool for writing modern JavaScript while ensuring compatibility with older browsers.
  - Setting up Babel in a Webpack project involves configuring Babel loader and presets.
  - Babel can transpile modern JavaScript features into ES5 syntax.
- Encourage students to explore more advanced Babel features in their own time.
