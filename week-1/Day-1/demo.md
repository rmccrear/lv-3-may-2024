<!--! Hour 1 -->

# Day 1: Installing Node.js and Exploring Terminal Outputs

## Hour 1: Demo Code and Instructions

### Part 1: Installing Node.js

**Narrative**: "Today, we're starting with the basics of backend development using Node.js, a powerful JavaScript runtime. Let's begin by installing Node.js on our machines."

1. **Navigate to Node.js official website**:

   - Explain: "Node.js can be downloaded from its official website. There are usually two versions available: LTS (Long Term Support) and Current. For stability and enterprise use, we recommend LTS."

2. **Download and Install Node.js**:
   - Command: _(Show the website and the download button but do not execute any command here.)_
   - Explain: "Once downloaded, run the installer and follow the on-screen instructions. The installer will set up Node.js and npm (Node Package Manager), which is crucial for managing our JavaScript packages."

### Part 2: Verifying Node.js Installation

**Narrative**: "After installation, it's important to verify that Node.js and npm are correctly installed on our system. Let's check their versions."

1. **Open Terminal (or Command Prompt on Windows)**:

   - Command: _(No command needed to open terminal; just navigate to it.)_
   - Explain: "The terminal is a direct line to our system where we can execute commands. For Windows users, Command Prompt or PowerShell works too."

2. **Check Node.js Version**:

   - Command: `node -v`
   - Explain: "This command checks the currently installed version of Node.js. The version number should be displayed, indicating a successful installation."

3. **Check npm Version**:
   - Command: `npm -v`
   - Explain: "Similarly, this command checks the version of npm installed on our system. npm is installed alongside Node.js and is essential for managing JavaScript packages."

### Part 3: Introduction to the Terminal

**Narrative**: "Now that we have Node.js installed, let's get familiar with the terminal by navigating directories and running a simple JavaScript file."

1. **Navigating Directories**:

   - Command: `cd <directory_path>`
   - Explain: "The `cd` command stands for 'change directory'. Use it to navigate into folders. For example, `cd Documents` will move you into the Documents directory."

2. **Creating Files**:

   - Command: `touch hello-world.js`
   - Explain: "The `touch` command creates a new file. Here, we're creating a JavaScript file named `hello-world.js`."

3. **Running a JavaScript File with Node.js**:
   - Command: `node hello-world.js`
   - Explain: "After writing our JavaScript code, we can run the file using the `node` command followed by the file name. This executes our script."

### Part 4: Coding a Simple Hello World Program

**Narrative**: "Let's write our first Node.js script to print 'Hello, World!' to the console."

1. **Open `hello-world.js` in a Text Editor**:

   - Explain: "Use any text editor you prefer. Visual Studio Code is a popular choice among developers for its rich features and extensions."

2. **Write the Hello World Script**:

   - Code Example:
     ```js
     console.log('Hello, World!');
     ```
   - Explain: "Here, we're using `console.log` to print a message to the terminal. It's a simple yet powerful way to debug and display information in JavaScript."

3. **Save and Run the Script**:
   - Command: `node hello-world.js`
   - Expected Output: `Hello, World!`
   - Explain: "Upon running the script, you should see 'Hello, World!' printed in the terminal. Congratulations, you've just run your first Node.js script!"

**Wrap-Up**: "That's it for the first part of today's session. We've successfully installed Node.js, verified the installation, and executed our first JavaScript code using Node. Next, we'll dive into initializing a Node.js project and exploring basic arithmetic operations with JavaScript."

<!--! Hour 2  -->

# Day 1: Installing Node.js and Exploring Terminal Outputs

## Hour 2: Demo Code and Instructions

### Part 1: Initializing a Node.js Project

**Narrative**: "With Node.js installed, let's move on to setting up our very first Node.js project using npm, which will help us manage our project's dependencies."

1. **Create a New Directory for the Project**:

   - Command: `mkdir myNodeProject && cd myNodeProject`
   - Explain: "The `mkdir` command creates a new directory. Here, we create a directory named `myNodeProject` and then navigate into it with `cd`."

2. **Initialize the Node.js Project**:
   - Command: `npm init -y`
   - Explain: "This command initializes a new Node.js project. The `-y` flag automatically fills out the package.json file with default values."

### Part 2: Creating a Basic Arithmetic Operations Script

**Narrative**: "Now that our project is set up, let's create a simple script that performs basic arithmetic operations based on command-line arguments."

1. **Create the Arithmetic Script File**:

   - Command: `touch arithmetic.js`
   - Explain: "We use the `touch` command again to create a new file named `arithmetic.js` where we'll write our arithmetic operations code."

2. **Open `arithmetic.js` in a Text Editor and Write the Script**:

   - Code Example:

     ```js
     // Parse command line arguments, excluding the first two (node and script path)
     const args = process.argv.slice(2);

     // Basic arithmetic functions
     const add = (a, b) => a + b;
     const subtract = (a, b) => a - b;
     const multiply = (a, b) => a * b;
     const divide = (a, b) => a / b;

     // Determine the operation based on the first argument
     const operation = args[0];
     const num1 = parseFloat(args[1]);
     const num2 = parseFloat(args[2]);

     // Perform the operation
     let result;
     switch (operation) {
       case 'add':
         result = add(num1, num2);
         break;
       case 'subtract':
         result = subtract(num1, num2);
         break;
       case 'multiply':
         result = multiply(num1, num2);
         break;
       case 'divide':
         result = divide(num1, num2);
         break;
       default:
         result = 'Unknown operation';
     }

     console.log(`Result: ${result}`);
     ```

   - Explain: "This script takes three command-line arguments: the operation (add, subtract, multiply, divide) and two numbers. It then performs the requested arithmetic operation on the numbers and prints the result."

3. **Run the Arithmetic Script with Node.js**:
   - Command: `node arithmetic.js add 5 3`
   - Expected Output: `Result: 8`
   - Explain: "By running this command, we're asking our script to add 5 and 3. You can replace `add` with `subtract`, `multiply`, or `divide` and change the numbers to see different results."

**Wrap-Up**: "Great work! We've now set up our first Node.js project and created a script that performs basic arithmetic operations based on command-line inputs. This is a fundamental step towards building more complex Node.js applications."
