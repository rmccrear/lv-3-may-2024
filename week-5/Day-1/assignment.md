# Assignment: Webpack Assignment 1

## Objective

This assignment aims to reinforce your understanding of Webpack by setting up a basic Webpack configuration in a new project. You will create a simple web application that uses Webpack to bundle JavaScript modules and includes basic configuration for handling CSS files.

## Instructions

### Part 1: Project Setup

1. **Initialize a New Project**:

   - Create a new directory called `webpack-basics`.
   - Navigate into your project directory and run `npm init -y` to create a new npm project.

2. **Install Webpack**:

   - Install Webpack and Webpack CLI as development dependencies by running `npm install --save-dev webpack webpack-cli`.

3. **Project Structure**:
   - Create a `src` directory for your source files.
   - Inside `src`, create an `index.js` file and a `styles.css` file.
   - Create a `dist` directory for your output files, and add an `index.html` file inside.

### Part 2: Webpack Configuration

1. **Webpack Configuration File**:

   - Create a `webpack.config.js` file in your project root.
   - Set up the entry point to your `src/index.js` and configure the output to a `bundle.js` file in the `dist` directory.

2. **Handling CSS**:
   - Install `style-loader` and `css-loader` by running `npm install --save-dev style-loader css-loader`.
   - Configure Webpack to use these loaders for `.css` files.

### Part 3: Implement Your Application

1. **JavaScript Functionality**:

   - In `src/index.js`, write a simple JavaScript function that adds a piece of text to the DOM.

2. **Styling**:

   - Add some basic styles in `src/styles.css` and import this CSS file in your `src/index.js`.

3. **HTML Setup**:
   - In `dist/index.html`, link your bundled JavaScript file. Ensure the HTML file has a root element where your JavaScript can add content.

### Part 4: Build and Test

1. **Building Your Project**:

   - Add a build script in your `package.json` to run Webpack (`"build": "webpack"`).
   - Run `npm run build` to bundle your application.

2. **Testing Your Application**:
   - Open `dist/index.html` in a browser to ensure that your JavaScript runs and styles are applied correctly.

## Submission

- **GitHub Repository**: Create a new repository on GitHub named `webpack-basics`. Push your project to this repository.
- **Include a `.gitignore`**: Ensure your `node_modules` directory is not included in your repository.
- **README**: Update the README.md file with a brief description of your project and instructions on how to build and run it.
- **Submit the Repository URL**: Provide the URL to your GitHub repository as your submission.

## Rubric

### Project Setup and Structure - 5 points

- **Complete (5 pts)**: Project is correctly set up with all required files and directories.
- **Partial (3 pts)**: Minor issues with project setup or structure.
- **Limited (1 pt)**: Significant issues with setup or missing key files/directories.

### Webpack Configuration - 5 points

- **Complete (5 pts)**: Webpack is correctly configured for JavaScript and CSS.
- **Partial (3 pts)**: Webpack configuration is mostly correct, with minor errors.
- **Limited (1 pt)**: Significant errors in Webpack configuration.

### JavaScript and CSS Implementation - 5 points

- **Complete (5 pts)**: JavaScript functionality and CSS styles are correctly implemented and working as intended.
- **Partial (3 pts)**: Minor issues in JavaScript or CSS implementation.
- **Limited (1 pt)**: Major issues with JavaScript functionality or CSS styles.

### Build and Functionality - 5 points

- **Complete (5 pts)**: Application builds successfully and runs as expected.
- **Partial (3 pts)**: Application mostly works but has minor issues.
- **Limited (1 pt)**: Application does not build or has significant runtime issues.

### Documentation and Repository Quality - 5 points

- **Complete (5 pts)**: README is well-written with clear build/run instructions. Repository is clean and organized.
- **Partial (3 pts)**: README is present but lacks detail. Minor issues with repository organization.
- **Limited (1 pt)**: Poor documentation and repository organization.
