## Assignment: Node Assignment 3

### Objective

Create a modular Node.js command-line survey tool that collects users' programming preferences using the Inquirer package. This tool will demonstrate your ability to structure code into modules for different survey questions and integrate user input handling in a cohesive application.

### Instructions

#### Step 1: Initialize Project and Repository

- **Create a GitHub Repository**:

  - Name the repository `Node-Assignment-3`. Initialize it with a README and a `.gitignore` file for Node.js.

- **Local Setup**:
  - Clone the repository and navigate into it.
  - Run `npm init -y` to create a `package.json` file.
  - Install Inquirer with `npm install inquirer`.

#### Step 2: Structure Your Survey

- **Create Modules for Questions**:
  - In your project, create a `questions` directory.
  - Inside `questions`, create modules (e.g., `favoriteLanguage.js`, `preferredFramework.js`) that export question objects for Inquirer. You will only need to export a JavaScript object for each module. See the example object:

```js
questionObject = {
  type: 'list',
  name: 'operation',
  message: 'Which operation would you like to perform?',
  choices: ['add', 'subtract', 'multiply', 'divide'],
};
module.exports = questionObject;
```

#### Step 3: Implement the Survey Tool

- **Build the Main Survey Application (`survey.js`)**:
  - Import the Inquirer package and your question modules.
  - Use Inquirer to prompt the user with the questions imported from your modules.

#### Step 4: Log User Responses

- **Capture and Display Responses**:
  - After collecting responses, log a summary to the console, thanking the user for their input and summarizing their preferences.

#### Step 5: Document and Finalize

- **Update README.md**:
  - Describe the survey tool, how to run it, and the purpose of each module.
  - Push changes to GitHub, ensuring `.gitignore` is properly set up to exclude `node_modules`.

### Rubric

#### Modular Question Design - 5 points

- Complete (5 pts): Questions are well-designed and stored in separate modules, demonstrating effective use of modular programming concepts.
- Partial (3 pts): Most questions are modularized, but the structure could be more cohesive or logical.
- Limited (0 pts): Questions are not effectively modularized or are largely contained within a single file.

#### Survey Tool Functionality - 5 points

- Complete (5 pts): The survey tool functions as intended, collecting user inputs through a series of prompts without errors.
- Partial (3 pts): The survey tool collects inputs but may have minor bugs or usability issues.
- Limited (0 pts): The tool does not function correctly or fails to collect user inputs as required.

#### Inquirer Integration - 5 points

- Complete (5 pts): Demonstrates proficient use of Inquirer, including various types of prompts and input validation where appropriate.
- Partial (3 pts): Basic use of Inquirer is evident, but lacks variety or sophistication in prompt types or validation.
- Limited (0 pts): Misuses Inquirer or significantly lacks complexity and validation in user prompts.

#### Code Quality and Organization - 5 points

- Complete (5 pts): Code is exceptionally well-organized, with clear naming conventions, logical structure, and adheres to best practices.
- Partial (3 pts): Generally well-organized code but with some areas for improvement in clarity, structure, or adherence to best practices.
- Limited (0 pts): Poorly organized code with unclear naming, lack of structure, or disregard for best practices.

#### Documentation and Repository Management - 5 points

- Complete (5 pts): Comprehensive README with clear instructions and descriptions; `.gitignore` properly excludes unnecessary files; clean repository structure.
- Partial (3 pts): README provides basic instructions and descriptions; minor issues with `.gitignore` or repository structure.
- Limited (0 pts): Inadequate README; `.gitignore` missing or ineffective; messy repository structure.
