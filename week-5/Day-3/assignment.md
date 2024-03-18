# Assignment: Webpack Assignment 3

## Objective

This assignment will solidify your understanding of Babel and its role in JavaScript transpilation. You'll configure Babel in a project, use ES6+ features in your JavaScript code, and transpile it for broader browser compatibility.

## Instructions

### Part 1: Setup and Configuration

1. **Initialize Your Project**:

   - Create a new directory named `babel-transpilation-project`.
   - Initialize a new npm project and create a basic project structure including a `src` folder for your JavaScript files.

2. **Install Babel**:

   - Install `@babel/core`, `@babel/cli`, and `@babel/preset-env` as development dependencies in your project.

3. **Configure Babel**:
   - Create a `babel.config.json` file in the root of your project. Configure it to use `@babel/preset-env`.

### Part 2: Writing Modern JavaScript

1. **Create JavaScript Files**:

   - Inside the `src` directory, create several JavaScript files (`index.js`, `module1.js`, and `module2.js`). Use ES6+ features such as arrow functions, template literals, `let`, `const`, classes, default parameters, destructuring, and modules (import/export).

2. **Implement Functionality**:
   - In `module1.js` and `module2.js`, define different functions or classes using ES6+ syntax. Export these modules.
   - In `index.js`, import the modules from `module1.js` and `module2.js`. Use their functionality and ensure your code utilizes a variety of ES6+ features.

### Part 3: Transpiling with Babel

1. **Transpile Your Code**:

   - Use Babel to transpile your code from the `src` directory into a new directory named `lib`.

2. **Run and Verify**:
   - Verify the transpiled code in the `lib` directory to ensure it's converted into a form compatible with older JavaScript versions.

### Part 4: Documentation

- **Update README.md**:
  - Document how to install dependencies, configure Babel, and transpile the project.
  - Include a brief explanation of how Babel transforms the modern JavaScript features used in your code to ensure compatibility with older browsers.

## Submission

- **GitHub Repository**: Create a repository on GitHub named `babel-transpilation-project`. Include your project files, excluding `node_modules` by using a `.gitignore` file.
- **Live Demonstration**: Include instructions for running the transpilation process in your README.md.
- **Repository URL**: Submit the URL of your GitHub repository.

## Rubric

### Project Setup and Babel Configuration - 5 points

- **Complete (5 pts)**: Correctly set up the project and Babel configuration with `@babel/preset-env`.
- **Partial (3 pts)**: Minor issues in setup or configuration.
- **Limited (1 pt)**: Significant setup or configuration errors.

### Modern JavaScript Usage - 5 points

- **Complete (5 pts)**: Effectively uses a variety of ES6+ features across the project.
- **Partial (3 pts)**: Uses some ES6+ features but lacks variety or complexity.
- **Limited (1 pt)**: Minimal or incorrect use of ES6+ features.

### Successful Transpilation - 5 points

- **Complete (5 pts)**: Code is successfully transpiled with Babel, and the output is correct.
- **Partial (3 pts)**: Transpilation is mostly successful, with minor issues in the output.
- **Limited (1 pt)**: Significant problems with transpilation output.

### Documentation and Explanation - 5 points

- **Complete (5 pts)**: Comprehensive README.md with clear instructions and explanations.
- **Partial (3 pts)**: README.md is present but lacks detail or clarity.
- **Limited (1 pt)**: Inadequate documentation or significant errors.

### Code Quality and Organization - 5 points

- **Complete (5 pts)**: Code is well-organized, readable, and follows best practices.
- **Partial (3 pts)**: Generally good code quality but with areas for improvement.
- **Limited (1 pt)**: Poor code organization or readability.
