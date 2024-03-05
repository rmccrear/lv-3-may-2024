# Day 2: Using NPM and Common Packages

<!--! Hour 1 -->

## Hour 1: Demo Code - Introduction to NPM and Lodash

### Part 1: Introduction to NPM

**Narrative**: "NPM stands for Node Package Manager, and it's a crucial tool for managing libraries and packages that extend the functionality of your Node.js projects. Today, we'll explore how to use NPM to include external packages in our project."

1. **Discuss the `package.json` File**:
   - Explain: "The `package.json` file is the heart of any Node.js project. It tracks the project's dependencies and contains metadata about the project, such as its name, version, and scripts."

### Part 2: Installing and Using Lodash

**Narrative**: "One common package that demonstrates the power of NPM is lodash, a utility library that makes JavaScript easier by taking the hassle out of working with arrays, numbers, objects, strings, etc."

1. **Install Lodash**:

   - Command: `npm install lodash`
   - Explain: "This command tells NPM to download lodash and add it as a dependency in our `package.json` file. It also creates a `node_modules` directory where the lodash package and its dependencies are stored."

2. **Explore Lodash Documentation**:
   - Narrative: "Let's briefly look at the lodash documentation to understand some of its core functionalities."
   - Action: _(Show the lodash documentation but do not execute any command. Highlight methods like `_.flattenDeep`and`_.uniq`.)_

### Part 3: Demonstrating Lodash in Action

**Narrative**: "Now, let's write some code to see lodash in action. We'll focus on array operations, specifically flattening a nested array and removing duplicate values."

1. **Create a New JavaScript File**:

   - Command: `touch lodash-demo.js`
   - Explain: "We'll create a new file named `lodash-demo.js` where we will demonstrate the use of lodash."

2. **Write the Demo Script Using Lodash**:

   - Open `lodash-demo.js` in a text editor and add the following code:

     ```js
     const _ = require('lodash');

     // Example array with nested arrays and duplicate values
     const exampleArray = [1, [2, [3, [4]], 5], 5, [6]];

     // Use lodash to flatten the array deeply
     const flattenedArray = _.flattenDeep(exampleArray);
     console.log('Flattened Array:', flattenedArray);

     // Use lodash to remove duplicate values
     const uniqueArray = _.uniq(flattenedArray);
     console.log('Unique Array:', uniqueArray);
     ```

   - Explain: "`require('lodash')` imports the lodash library. We then use `_.flattenDeep` to flatten the nested array and `_.uniq` to remove duplicate values. This demonstrates the power of lodash in simplifying complex array operations."

3. **Run the Script**:
   - Command: `node lodash-demo.js`
   - Expected Output:
     ```
     Flattened Array: [1, 2, 3, 4, 5, 5, 6]
     Unique Array: [1, 2, 3, 4, 5, 6]
     ```
   - Explain: "The output shows our nested array flattened into a single level and then all duplicate values removed. Lodash makes these operations straightforward and concise."

**Wrap-Up**: "This hour, we've introduced NPM and demonstrated how to use it to integrate lodash into our project. Lodash is just one example of how external packages can greatly enhance our JavaScript applications. Next, we'll explore another powerful package, Inquirer, to interact with users through the command line."

<!--! Hour 2  -->

# Day 2: Using NPM and Common Packages

## Hour 2: Demo Code - Introduction to Inquirer

### Part 1: Introduction to Inquirer

**Narrative**: "After exploring how lodash can simplify array operations, let's shift our focus to creating interactive command-line applications. We'll use the Inquirer.js package, which makes it easy to capture user input in the terminal."

1. **Install Inquirer**:
   - Command: `npm install inquirer`
   - Explain: "This command installs the Inquirer package and adds it as a dependency in our project. Inquirer is a powerful tool for building a user-friendly command-line interface."

### Part 2: Building a Simple Script with Inquirer

**Narrative**: "Now, we'll create a script that uses Inquirer to prompt the user for their name and favorite color, and then responds with a personalized message in the console."

1. **Create a New JavaScript File for the Inquirer Demo**:

   - Command: `touch user-interaction.js`
   - Explain: "We'll create a new file named `user-interaction.js` to hold our Inquirer demonstration code."

2. **Write the Inquirer Script**:

   - Open `user-interaction.js` in a text editor and add the following code:

     ```js
     const inquirer = require('inquirer');

     // Array of questions for user input
     const questions = [
       {
         type: 'input',
         name: 'name',
         message: 'What is your name?',
       },
       {
         type: 'input',
         name: 'color',
         message: 'What is your favorite color?',
       },
     ];

     // Use Inquirer to prompt the questions to the user
     inquirer.prompt(questions).then((answers) => {
       console.log(
         `Hello, ${answers.name}! Your favorite color is ${answers.color}.`
       );
     });
     ```

   - Explain: "This script uses `inquirer.prompt` to display questions to the user and captures their responses. The responses are then used in a template literal to construct a personalized message."

3. **Run the Script**:
   - Command: `node user-interaction.js`
   - Action: Demonstrate how the script prompts for the user's name and favorite color, then outputs a message based on the input.
   - Explain: "The Inquirer library simplifies collecting and handling user input, allowing us to create more interactive and engaging command-line applications."

### Part 3: Understanding `package-lock.json` and Node Modules

**Narrative**: "With both lodash and Inquirer added to our project, you've noticed a `package-lock.json` file and a `node_modules` directory. Let's briefly discuss their significance."

1. **The `package-lock.json` File**:

   - Explain: "The `package-lock.json` file locks the versions of installed packages and their dependencies. This ensures consistency and reliability across installations, as it precisely records what was installed."

2. **The `node_modules` Directory**:
   - Explain: "The `node_modules` directory contains the installed packages. It's automatically created by npm and houses the library files our project depends on. This directory should not be included in version control; hence, it's listed in `.gitignore`."

**Wrap-Up**: "In this hour, we've introduced Inquirer to create interactive CLI applications and touched upon the `package-lock.json` file and `node_modules` directory. These tools and concepts are foundational in Node.js development, enhancing our ability to build and manage robust applications."
