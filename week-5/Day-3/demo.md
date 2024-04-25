## Day 3: Introduction to Babel and JavaScript Transpilation

### Hour 1: Understanding JavaScript Transpilation with Babel

Today, we're focusing on Babel—a powerful tool that lets us write modern JavaScript that works across all browsers. Babel converts ES6+ code into backwards-compatible versions, ensuring broad compatibility.
Right after introducing Babel and its purpose, let's dive into some ES6 syntax examples that Babel can convert into backwards-compatible JavaScript. This will give you a clearer understanding of how Babel allows us to use modern JavaScript features without worrying about browser support.

#### Why Babel?

JavaScript evolves rapidly, introducing new syntax and features that improve the developer experience and code efficiency. However, not all users' browsers support the latest JavaScript features. This is where Babel comes in, allowing us to use next-gen JavaScript without worrying about browser support.

#### Setting Up Babel

First, we need to initialize a new npm project and install Babel:

1. **Initialize a New Project**:
   Open your terminal, create a new directory for your project, and navigate into it:

   ```bash
   mkdir babel-demo
   cd babel-demo
   npm init -y
   touch index.js
   ```

   This command creates a new npm project with default settings.

### ES6 Syntax Examples

ES6 (ECMAScript 2015) introduced many updates to JavaScript, including new syntax and features for more expressive and concise code. Here are a few examples of ES6 syntax that Babel can transpile:

1. **Arrow Functions**:
   ES6 introduced arrow functions, a concise way to write function expressions.

   ```js
   // ES6 Arrow Function
   const add = (a, b) => a + b;
   ```

   Babel transpiles this to a traditional function expression for broader compatibility.

2. **Template Literals**:
   Template literals provide an easy way to interpolate variables and expressions into strings.

   ```js
   // ES6 Template Literal
   const name = 'Babel';
   console.log(`Hello, ${name}!`);
   ```

3. **Let and Const**:
   `let` and `const` introduce block-scoped variable declarations, with `const` being for constants.

   ```js
   // ES6 let and const
   let score = 0;
   const playerName = 'Alice';
   ```

4. **Classes**:
   ES6 classes provide a syntactic sugar for prototypal inheritance but don't introduce a new object-oriented inheritance model.

   ```js
   // ES6 Class
   class Person {
     constructor(name) {
       this.name = name;
     }

     greet() {
       console.log(`Hello, my name is ${this.name}`);
     }
   }
   ```

5. **Default Parameters**:
   Functions can have default parameter values.

   ```js
   // ES6 Default Parameters
   function greet(name = 'World') {
     console.log(`Hello, ${name}!`);
   }
   ```

6. **Destructuring Assignment**:
   Destructuring allows binding using pattern matching, with support for matching arrays and objects.

   ```js
   // ES6 Destructuring Assignment
   const { firstName, lastName } = { firstName: 'John', lastName: 'Doe' };
   console.log(firstName); // Output: John
   ```

7. **Modules (Import/Export)**:
   ES6 modules allow for the modularization of JavaScript code.

   ```js
   // ES6 Import/Export
   // In file math.js
   export const add = (a, b) => a + b;

   // In another file
   import { add } from './math';
   console.log(add(2, 3));
   ```

Each of these features enhances JavaScript's expressiveness and can be seamlessly integrated into your projects with Babel's help. By transpiling this syntax to ES5, Babel ensures that your codebase remains compatible with older browsers, broadening your application's reach. 2. **Install Babel**:
Install Babel core and the preset for environment:

```bash
npm install --save-dev @babel/core @babel/cli @babel/preset-env
```

- `@babel/core` is the main part of Babel
- `@babel/cli` is the command-line interface for Babel
- `@babel/preset-env` is a smart preset that allows you to use the latest JavaScript.

3. **Create a Babel Configuration File**:
   Babel needs to know how you want to transform your code. Create a `babel.config.json` file in the root of your project:
   From the docs: https://babeljs.io/docs/usage
   ```json
   {
     "presets": [
       [
         "@babel/preset-env",
         {
           "targets": {
             "edge": "17",
             "firefox": "60",
             "chrome": "67",
             "safari": "11.1"
           },
           "useBuiltIns": "usage",
           "corejs": "3.6.5"
         }
       ]
     ]
   }
   ```
   This tells Babel to use the preset-env, which transforms your JavaScript to be compatible with over 90% of browsers globally.

#### Writing Modern JavaScript

Create a new file `src/index.js` and add some modern JavaScript code. For example:

```js
// src/index.js
const greet = (name) => `Hello, ${name}!`;
console.log(greet('World'));
```

#### Transpiling with Babel

Now, let's transpile our modern JavaScript to something more universally compatible:

1. **Run Babel**:
   To transpile your `src/index.js`, run:

   ```bash
   ./node_modules/.bin/babel src --out-dir lib
   ```

   This command reads the JavaScript files in `src/`, transpiles them using the configuration defined in `.babelrc`, and outputs the result to `lib/`.

2. **Check the Output**:
   Open `lib/index.js` to see the transpiled code. You should notice that the arrow function has been transformed into a function expression or declaration, depending on the specific features used and the browsers you're targeting.

#### Conclusion

Babel is a cornerstone tool in modern web development, allowing us to leverage the full power of the latest JavaScript features while ensuring our applications remain accessible to all users. By setting up Babel in our projects, we make a significant step towards writing cleaner, more efficient code without sacrificing compatibility.

<!--! Hour 2 -->

## Day 3: Introduction to Babel and JavaScript Transpilation

### Hour 2: Delving Deeper into Babel's Power

Now that we've set the stage with Babel's basics, let's explore how to fine-tune our setup with presets and plugins, and understand the crucial role of polyfills in ensuring broader compatibility. We'll also correct our configuration file naming to the more recent `babel.config.json`.

#### Babel Presets: A Closer Look

Babel presets are essentially bundles of plugins. Each preset is a set of rules for how to transform your JavaScript code. One of the most powerful and commonly used presets is `@babel/preset-env`, which intelligently decides which transformations and polyfills are necessary based on your target environments.

1. **Configuring `@babel/preset-env`**:
   This preset simplifies the process of ensuring your JavaScript is compatible across different environments. It reads your compatibility targets (e.g., browsers you want to support) and includes the necessary polyfills and syntax transformations.


   Then, configure Babel by creating a `babel.config.json` file in your project's root:

   ```json
   {
     "presets": ["@babel/preset-env"]
   }
   ```

2. **Understanding Browser Targets and Polyfills**:
   You can specify which environments your project needs to support using the `browserslist` field in your `package.json`. This is crucial for determining which polyfills are needed.

   ```json
   "browserslist": [
     ">0.25%",
     "not dead"
   ]
   ```

   **Polyfills**: These are snippets of code that add missing features to older browsers. When `@babel/preset-env` is configured, it automatically includes necessary polyfills for the features used in your code based on your `browserslist`.

#### Dive into Babel Plugins

While presets are collections of plugins designed for specific environments, individual Babel plugins offer more granular transformations.

1. **Example: Transform Arrow Functions**:
   To illustrate, let's use a plugin that transforms ES6 arrow functions into function expressions, ensuring compatibility with older JavaScript engines.

   ```bash
   npm install --save-dev @babel/plugin-transform-arrow-functions
   ```

   Add this plugin to your `babel.config.json`:

   ```json
   {
     "plugins": ["@babel/plugin-transform-arrow-functions"]
   }
   ```

#### Practical Demonstration

Let's see Babel in action with an example that will be transformed by our setup.

1. **Create a JavaScript File**:
   In `src/example.js`, write some modern JavaScript:

   ```js
   const greet = (name) => `Hello, ${name}!`;
   console.log(greet('Babel'));
   ```

2. **Transpile the Code**:
   Run Babel to transpile your `src` directory:

   ```bash
   npx babel src --out-dir lib
   ```

3. **Review the Output**:
   Check `lib/example.js` for the transpiled version. The arrow function should now be a function expression, showing Babel's transformation in action.

#### Conclusion

By leveraging Babel's presets and plugins, and understanding the importance of polyfills, you're equipped to write modern, clean JavaScript without worrying about browser incompatibilities. This setup ensures your applications can reach a wider audience while you enjoy the benefits of the latest JavaScript features.
