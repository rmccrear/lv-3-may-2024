# Day 3: Modular JavaScript and Interactive CLI Applications

## Hour 1: Expanding on Modules and Inquirer Integration

### Review and Introduction

**Narrative**: "Let's quickly review modules and the Inquirer package. Modules help organize code into reusable segments, and Inquirer allows us to build interactive CLI applications. Today, we'll combine these concepts to create a modular, interactive arithmetic application."

### Step 1: Setting Up Our Project Environment

1. **Ensure Project Initialization**:

   - Review: "Make sure our Node.js project is initialized (`npm init`) and that we have Inquirer installed (`npm install inquirer`)."

2. **Create a 'lib' Directory for Our Modules**:
   - Command: `mkdir lib`
   - Explain: "We'll store our custom JavaScript modules in a `lib` directory to keep our project organized."

### Step 2: Creating Arithmetic Modules

1. **Build Arithmetic Modules**:
   - Action: Create files for each arithmetic operation inside the `lib` directory (`add.js`, `subtract.js`, `multiply.js`, `divide.js`).
   - Example for `add.js`:
     ```javascript
     // lib/add.js
     const add = (a, b) => a + b;
     module.exports = add;
     ```
   - Explain: "Each module will export a function for an arithmetic operation. This promotes code reusability and separation of concerns."

### Step 3: Integrating Inquirer to Collect User Inputs

1. **Set Up Inquirer to Ask for the Operation and Numbers**:

   - File: Create a main application file, e.g., `calculator.js`.
   - Code Setup: Use Inquirer in `calculator.js` to ask the user which arithmetic operation they'd like to perform and for two numbers.
   - Inquirer Setup Example:

     ```javascript
     // calculator.js
     const inquirer = require('inquirer');
     const add = require('./lib/add');

     const questions = [
       {
         type: 'list',
         name: 'operation',
         message: 'Which operation would you like to perform?',
         choices: ['add', 'subtract', 'multiply', 'divide'],
       },
       {
         type: 'input',
         name: 'number1',
         message: 'Enter the first number:',
         validate: function (value) {
           var valid = !isNaN(parseFloat(value));
           return valid || 'Please enter a number';
         },
         filter: Number,
       },
       {
         type: 'input',
         name: 'number2',
         message: 'Enter the second number:',
         validate: function (value) {
           var valid = !isNaN(parseFloat(value));
           return valid || 'Please enter a number';
         },
         filter: Number,
       },
     ];

     inquirer.prompt(questions).then((answers) => {
       let result;
       switch (answers.operation) {
         case 'add':
           result = add(answers.number1, answers.number2);
           break;
         // Include cases for subtract, multiply, and divide
       }
       console.log(`The result is ${result}`);
     });
     ```

   - Explain: "This setup demonstrates how to use Inquirer to interactively collect inputs for our operations. It also shows the importance of validating and filtering user inputs to ensure they can be used in our calculations."

### Step 4: Discussing Modular Architecture and Code Reusability

1. **Emphasize the Benefits of Modular Design**:

   - Explain: "By structuring our project into modules, we enhance its maintainability. Each module has a single responsibility and can be easily tested and reused."

2. **Highlight Inquirer's Role in CLI Applications**:
   - Discuss: "Inquirer makes our applications user-friendly, allowing for a wide range of input types and validations, which is crucial for CLI tools."

**Wrap-Up**: "In this hour, we've taken significant steps in combining JavaScript modules and Inquirer to create a structured, interactive application. This modular approach not only makes our code cleaner and more maintainable but also enhances the user experience by making our CLI applications more dynamic and responsive to user input."

<!--! Hour 2  -->

# Day 3: Modular JavaScript and Interactive CLI Applications

## Hour 2: Enhancing the Application and Advanced Module Usage

### Expanding Our Arithmetic Operations

**Narrative**: "Now that we have a basic structure in place, let's enhance our application by adding more operations and refining our modular approach."

### Step 1: Adding More Arithmetic Modules

1. **Complete Arithmetic Module Implementations**:
   - Action: Implement the remaining arithmetic operations (`subtract.js`, `multiply.js`, `divide.js`) in the `lib` directory, similar to `add.js`.
   - Example for `subtract.js`:
     ```javascript
     // lib/subtract.js
     const subtract = (a, b) => a - b;
     module.exports = subtract;
     ```
   - Explain: "Creating separate modules for each operation follows the Single Responsibility Principle, making our codebase clean and maintainable."

### Step 2: Incorporating Error Handling

1. **Implement Basic Error Handling in Operations**:
   - Example: Update `divide.js` to handle division by zero.
     ```javascript
     // lib/divide.js
     const divide = (a, b) => {
       if (b === 0) {
         throw new Error('Division by zero is not allowed.');
       }
       return a / b;
     };
     module.exports = divide;
     ```
   - Explain: "Proper error handling is crucial in creating reliable applications. This step ensures our calculator can gracefully handle exceptional cases, such as division by zero."

### Step 3: Refining the Main Application with Advanced Imports

1. **Dynamically Import Modules Based on User Input**:
   - Update `calculator.js` to import arithmetic modules dynamically.
   - Code Update in `calculator.js`:
     ```javascript
     // Dynamically require the arithmetic module based on the operation
     inquirer.prompt(questions).then((answers) => {
       const operationModule = require(`./lib/${answers.operation}`);
       try {
         const result = operationModule(answers.number1, answers.number2);
         console.log(`The result is ${result}`);
       } catch (error) {
         console.error(`Error: ${error.message}`);
       }
     });
     ```
   - Explain: "This approach demonstrates how to dynamically require modules in Node.js, allowing our application to import and use the correct module based on the user's operation choice."

### Step 4: Discussion on Modular Project Organization

1. **Best Practices for Module Organization**:

   - Discuss: "Organizing modules in a logical structure (e.g., keeping all arithmetic operations in a `lib` directory) simplifies navigation and maintenance of the codebase."

2. **The Importance of Clear Module Interfaces**:
   - Explain: "Each module exports a clear interface (e.g., a single function), making it easy to understand and use elsewhere in our application."

**Wrap-Up**: "During this hour, we've significantly expanded the capabilities of our calculator application. We've added more operations, introduced error handling, and refined our use of modules. This modular and interactive CLI application is becoming a robust tool, showcasing the power of combining Node.js modules with Inquirer for building complex command-line applications."
