# Assignment: Webpack Assignment 1

## Objective

This assignment will help you understand Webpack by creating a simple web application that writes a message to the page and uses Lodash to modify it. You will first try to accomplish this without Webpack to see the errors that occur, then set up Webpack to resolve these errors.

## Instructions

### Part 1: Create the Basic App (Without Webpack)

1. **Set Up a New Project**:

   - Create a new directory called `webpack-demo`.
   - Navigate into your project directory and run `npm init -y` to create a new npm project.

2. **HTML Structure**:

   - Create a `dist/index.html` file with the following content:

     ```html
     <!DOCTYPE html>
     <html lang="en">
       <head>
         <title>Simple App Without Webpack</title>
       </head>
       <body>
         <div id="content">Initial Text</div>
         <script src="src/index.js"></script>
       </body>
     </html>
     ```

3. **JavaScript Functionality**:

   - Create a `src/index.js` file and add the following code:

     ```js
     document.getElementById('content').innerText = 'Hello, World!';

     import _ from 'lodash';
     const newText = _.camelCase('hello world');
     document.getElementById('content').innerText = newText;
     ```

4. **Observe the Error**:
   - Open `dist/index.html` in your browser and check the console. You should see an error because Lodash isn't installed or bundled. Take a screenshot of the error message for your assignment submission.

### Part 2: Set Up Webpack and Fix the Error

1. **Install Webpack**:

   - In your project directory, run `npm install --save-dev webpack webpack-cli`.

2. **Create a Webpack Configuration File**:

   - In your project root, create a `webpack.config.js` file with the following content:

     ```js
     const path = require('path');

     module.exports = {
       entry: './src/index.js',
       output: {
         filename: 'bundle.js',
         path: path.resolve(__dirname, 'dist'),
       },
       mode: 'development',
     };
     ```

3. **Bundle with Webpack**:

   - Add a build script in your `package.json`: `"build": "webpack"`.
   - Run `npm run build` to bundle your application. This should resolve the Lodash error by bundling the dependencies.

4. **Verify the Application**:
   - Open `dist/index.html` in your browser and ensure that the text is updated to camel casing without errors.
   - Take a screenshot of the successful output for your assignment submission.

### Part 3: Assignment Submission

- **GitHub Repository**:
  - Create a new GitHub repository named `webpack-demo` and push your project.
  - Ensure you have a `.gitignore` file to exclude `node_modules`.
- **README**:
  - Include a README.md with a brief description of your project, build instructions, and a link to your error screenshot.
- **Submit the Repository URL**:
  - Provide the URL to your GitHub repository for assignment submission.

### Assignment Rubric - Total 25 points

This rubric will help you evaluate your submission based on five key areas: Project Setup, Webpack Configuration, Application Functionality, Documentation, and GitHub Repository. Each area is worth 5 points.

#### Project Setup and Structure - 5 points

- **5 points**: Project setup is correct, with all required files and directories. The structure is organized and clean.
- **3 points**: Minor issues with project setup or missing some directories.
- **1 point**: Major issues with project structure, with significant missing files or directories.

#### Webpack Configuration - 5 points

- **5 points**: Webpack is configured properly with the correct entry point, output file, and other essential settings.
- **3 points**: Webpack configuration has minor errors but generally works.
- **1 point**: Major errors in the Webpack configuration, resulting in an unsuccessful build or incorrect output.

#### Application Functionality - 5 points

- **5 points**: The application runs without errors, and the expected functionality is achieved (Lodash working with camel casing).
- **3 points**: The application generally works, with some minor issues or inconsistencies.
- **1 point**: The application has significant errors or fails to run as intended.

#### Documentation - 5 points

- **5 points**: README is well-written, with clear instructions for building and running the project. It includes all required details and a screenshot of the console error.
- **3 points**: README is present but lacks some information or clarity in instructions.
- **1 point**: README is poorly written or missing essential information.

#### GitHub Repository Quality - 5 points

- **5 points**: Repository is clean, well-organized, and has a clear `.gitignore` to exclude `node_modules`. The repository has a descriptive name and a README file.
- **3 points**: Repository has minor organization issues or lacks a clear `.gitignore`.
- **1 point**: Repository is disorganized or lacks basic GitHub setup.
