# Week 1: Advanced JavaScript and Node.js Ecosystem

## Day 1: Installing Node.js and Exploring Terminal Outputs

### Hour 1: Demo Code
- Demonstrate how to download and install Node.js from the official website.
- Walkthrough of Node.js installation verification using `node -v` and `npm -v` commands.
- Introduction to the terminal: navigating directories, creating files, and running a simple `.js` file with `node yourfile.js`.
- **Code Example**: `hello-world.js` that prints "Hello, World!" to the console.

### Hour 2: Demo Code
- Explain the process of initializing a Node.js project with `npm init`.
- Show how to create a basic arithmetic operations script that takes command-line arguments.
- Discuss the difference between logging in the browser vs. the terminal.
- **Code Example**: `arithmetic.js` that can add, subtract, multiply, and divide based on command-line inputs.

### Hour 3: Hands-On Practice
- Students work on setting up their Node.js environment and replicate the `hello-world.js` and `arithmetic.js`.
- Instructor circulates to help with installation issues and understanding terminal commands.
- **Assignment**: Modify `arithmetic.js` to include exponentiation and modulus operations.

## Day 2: Using NPM and Common Packages

### Hour 1: Demo Code
- Introduction to NPM and the purpose of the `package.json` file.
- Demonstrate the installation of Lodash and its use in simplifying complex array operations.
- Briefly show the documentation of Lodash to highlight utility functions.
- **Code Example**: Using Lodash to perform operations like `_.flattenDeep(array)` and `_.uniq(array)`.

### Hour 2: Demo Code
- Introduce Inquirer, showcasing how to prompt users for input in a Node.js application.
- Build a simple script that uses Inquirer to gather user data and respond with personalized messages.
- Explain the significance of `package-lock.json` and node modules.
- **Code Example**: `user-interaction.js` using Inquirer to ask for the user's name and favorite color, then responding in the console with a customized message.

### Hour 3: Hands-On Practice
- Students create their CLI application that uses Inquirer to conduct a brief survey (e.g., favorite book, movie, etc.).
- Instructor is available for troubleshooting and explaining package concepts.
- **Assignment**: Enhance the survey app to include data validation and conditional questions based on previous answers.

## Day 3: Modular JavaScript

### Hour 1: Demo Code
- Explain the concept of modules in JavaScript and their scope.
- Demonstrate how to export functions from one file and import them into another using `require`.
- Walkthrough the creation of a utility module that could be used across different scripts.
- **Code Example**: `math-utils.js` module exporting functions like `add`, `subtract`, `multiply`, `divide`.

### Hour 2: Demo Code
- Show how to structure a project into multiple modules for better organization and maintenance.
- Build a small application that imports and uses the `math-utils.js` module for various operations.
- Discuss module caching and the importance of modular architecture.
- **Code Example**: `calculator-app.js` that imports `math-utils.js` and allows the user to perform operations via the terminal.

### Hour 3: Hands-On Practice
- Students refactor their existing `arithmetic.js` script into modular code.
- Instructor provides assistance with module exports/imports and file structuring.
- **Assignment**: Create a new module that extends the functionality of the calculator app, such as incorporating complex mathematical operations or conversions.

## Day 4: Publishing to NPM

### Hour 1: Demo Code
- Walkthrough the process of setting up an NPM account and initializing a project for publishing.
- Discuss the importance of README.md, licensing, and versioning.
- Show how to create a simple package and explain the `.npmignore` file.
- **Code Example**: Preparing a `string-utils` package with basic string manipulation functions ready for publishing.

### Hour 2: Demo Code
- Demonstrate the actual process of publishing the package to NPM using `npm publish`.
- Explain how to update a package with `npm version` and republish.
- Discuss post-publish considerations, such as managing issues and updates.
- **Code Example**: Update the `string-utils` package with additional functions and publish the new version.

### Hour 3: Hands-On Practice
- Students work on packaging their utility modules from the previous day and prepare them for publishing.
- Instructor supports students with account setup, package configuration, and publishing.
- **Assignment**: Publish their utility module to NPM and then import and use it in a separate project to verify it works.

## Day 5: Review of Node.js and Modules

### Hour 1: Demo Code
- Review the week's topics with a focus on practical examples and common pitfalls.
- Go over the process of requiring local vs. NPM-hosted modules.
- Reiterate the importance of modular code in large-scale applications.
- **Code Example**: Showcase a complex application that requires multiple local and external modules.

### Hour 2: Demo Code
- Deep dive into more advanced Inquirer usage, such as handling lists, checkboxes, and validation.
- Show how to integrate the utility modules created earlier in the week with Inquirer to build a more complex CLI application.
- **Code Example**: `survey-app.js` with enhanced Inquirer prompts that utilize utility modules for data processing.

### Hour 3: Hands-On Practice
- Students are given time to complete any unfinished assignments.
- Instructor is available for Q&A, helping students with any concepts they are still unsure about.
- **Assignment**: Extend the `survey-app.js` to include more complex question types and incorporate error handling.

