# Assignment: Webpack Assignment 4

## Objective

Enhance your JavaScript application by integrating advanced Babel and Webpack configurations. This assignment focuses on applying dynamic imports for code splitting and optimizing your bundle size through tree shaking.

## Instructions

### Part 1: Project Setup

1. **Initialize Your Project**:

   - Create a new directory named `advanced-babel-webpack`.
   - Initialize a new npm project within this directory.

2. **Install Dependencies**:
   - Install Webpack, Babel, and necessary loaders and plugins as development dependencies.

### Part 2: Configuring Webpack and Babel

1. **Webpack Configuration**:

   - Create a `webpack.config.js` file.
   - Configure an entry point, output directory, and include Babel loader for processing JavaScript files.
   - Enable the `splitChunks` optimization in your Webpack configuration.

2. **Babel Configuration**:

   - Set up babel as a loader within the webpack

### Part 3: Implementing Features

1. **Dynamic Imports**:

   - Create a JavaScript module that exports a function or class. This module should not be needed immediately upon loading the application.
   - In your main JavaScript file, implement a dynamic import that loads the module only when it is needed (e.g., in response to a user action like clicking a button).

2. **Tree Shaking**:
   - In your JavaScript code, make use of ES6 import/export syntax.
   - Include some functions or classes that are not used.
   - Configure Webpack in production mode to enable tree shaking.

### Part 4: Building and Testing

1. **Build Your Application**:

   - Use Webpack to build your application.
   - Ensure that dynamic imports are correctly creating separate chunks.
   - Verify that unused code is removed from the final bundle as a result of tree shaking.

2. **Test Your Application**:
   - Serve your `dist` directory and test the dynamic loading functionality.
   - Observe the network activity to confirm code splitting is working as expected.

### Part 5: Documentation

- **Update README.md**:
  - Document the steps for setting up the project, including installing dependencies and configuring Webpack and Babel.
  - Describe how to build and test the project, including how to verify dynamic imports and tree shaking.

## Submission

- **GitHub Repository**: Push your project to a GitHub repository and ensure it includes a `.gitignore` file configured to exclude `node_modules`.
- **Repository URL**: Submit the URL of your GitHub repository.

## Rubric

### Webpack and Babel Configuration - 5 points

- **Complete (5 pts)**: Correctly configured Webpack and Babel for ES6+ JavaScript and dynamic imports.
- **Partial (3 pts)**: Configuration is mostly correct, with minor issues.
- **Limited (1 pt)**: Significant configuration errors or omissions.

### Implementation of Dynamic Imports - 5 points

- **Complete (5 pts)**: Successfully implemented dynamic imports, with code splitting evident in the build output.
- **Partial (3 pts)**: Dynamic imports implemented, but code splitting not effectively demonstrated or tested.
- **Limited (1 pt)**: Failed to implement dynamic imports correctly.

### Tree Shaking Effectiveness - 5 points

- **Complete (5 pts)**: Tree shaking correctly configured and demonstrated, with unused code removed from the bundle.
- **Partial (3 pts)**: Some evidence of tree shaking, but unused code not fully removed.
- **Limited (1 pt)**: Tree shaking not effectively configured or demonstrated.

### Project Documentation - 5 points

- **Complete (5 pts)**: Comprehensive README.md with clear setup, configuration, and testing instructions.
- **Partial (3 pts)**: README.md contains basic instructions but lacks detail or clarity.
- **Limited (1 pt)**: Inadequate documentation of the project setup and testing procedures.

### Code Quality and Organization - 5 points

- **Complete (5 pts)**: High-quality, well-organized code that follows best practices.
- **Partial (3 pts)**: Generally good code quality but with some areas for improvement in organization or adherence to best practices.
- **Limited (1 pt)**: Poor code quality or organization.
