## Assignment: Node Assignment 2

### Objective

Demonstrate your understanding of the Inquirer package by creating a simple command-line application that gathers user opinions through interactive prompts. This application should ask the user a series of questions about their preferences on various topics, showcasing your ability to handle user input in Node.js.

### Instructions

#### Step 1: Initialize Your GitHub Repository

- **Create a New GitHub Repository**:
  - Name the repository `Node-Assignment-2`.
  - Initialize it with a README file.

#### Step 2: Clone the Repository and Set Up Your Project

- **Clone Your Repository**:

  - Use the `git clone` command followed by the URL of your new repository to clone it to your local machine.

- **Project Setup**:
  - Navigate into your project directory (`cd Node-Assignment-2`) and run `npm init -y` to initialize a new Node.js project.

#### Step 3: Install Inquirer

- **Add Inquirer to Your Project**:
  - Run `npm install inquirer` to install the Inquirer package, which will be used to create the interactive prompts.

#### Step 4: Create the Opinion Poll

- **Write the Application Script**:
  - In the root of your project directory, create a file named `opinionPoll.js`.
  - Implement a series of prompts using Inquirer to ask the user for their opinions. The questions should include:
    1. A personalization question: "What is your name?" (input type)
    2. An opinion question on programming languages: "What's your favorite programming language?" (list type with options like "JavaScript", "Python", "Ruby", "Other")
    3. A question about preferred development tool: "Which editor do you prefer?" (list type with options like "VS Code", "Sublime Text", "Atom", "Other")
    4. An open-ended opinion question: "What's one feature you wish your editor had?" (input type)

#### Step 5: Log User Responses

- **Display the Results**:
  - After the user answers all questions, use console.log to display a summary of their responses, enhancing the interactive experience.

#### Step 6: Update the README and Push Your Changes

- **Document Your Project**:

  - Update the README.md file with instructions on how to install and run your opinion poll application.
  - Include a brief description of what the application does.

- **Push to GitHub**:
  - Use `git add .`, `git commit -m "Complete Node Assignment 2"`, and `git push` to push your local changes to the GitHub repository.

### Rubric

#### Inquirer Usage and Question Implementation - 10 points

- Complete (10 pts): Implements all required questions using Inquirer with correct types and options. The application runs smoothly without errors.
- Partial (5 pts): Implements most questions correctly, but may miss one question type or have minor issues.
- Limited (0 pts): Fails to implement questions as specified or application does not run.

#### Code Quality - 5 points

- Complete (5 pts): Code is clean, well-organized, and follows best practices.
- Partial (2 pts): Code is mostly clean but may have some minor issues with organization or readability.
- Limited (0 pts): Code is disorganized, difficult to read, or does not follow best practices.

#### Documentation (README.md) - 5 points

- Complete (5 pts): README.md clearly explains how to run the application, its purpose, and its features.
- Partial (2 pts): README.md provides basic instructions but lacks clarity or completeness.
- Limited (0 pts): README.md is unclear, incomplete, or missing.

#### Git and GitHub Usage - 5 points

- Complete (5 pts): Project is properly pushed to GitHub, including a meaningful commit history and excluding `node_modules`.
- Partial (2 pts): Project is on GitHub, but commit history is minimal or `node_modules` is included.
- Limited (0 pts): Project is not on GitHub, has no commit history, or is improperly set up.
