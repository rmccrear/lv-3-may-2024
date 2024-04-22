# Week 5, Day 1, Hour 1: Introduction to Webpack

Today, we're diving into Webpack, a powerful tool that has transformed the way we develop modern web applications. We'll start from the basics, understanding its role, and how to get a simple project up and running.

## What is Webpack?

Webpack is a static module bundler for JavaScript applications. It takes modules with dependencies and generates static assets representing those modules.(Show the node_modules here to show what dependencies are) It's widely used in the industry to bundle JavaScript files and assets like CSS, images, and more into a single or multiple bundles that can be easily used in a web environment.

### Why Use Webpack?

- **Efficiency**: Bundles multiple files into fewer bundles, reducing load times.
- **Modularity**: Encourages writing modular code, improving maintainability.
- **Optimization**: Offers powerful tools for optimizing your application for production.

## Setting Up a New Project with Webpack

To get started, we'll set up a new project and configure Webpack. Follow these steps:

### Step 1: Create a New Project

Open your terminal and create a new directory for your project, then navigate into it:

```bash
mkdir webpack-demo
cd webpack-demo
```

Initialize a new npm project:

```bash
npm init -y
```

This command creates a `package.json` file in your project directory.

### Step 2: Install Webpack

To harness the power of Webpack in our project, we need to install two key pieces of software: Webpack itself and the Webpack Command Line Interface (CLI).

#### Why Webpack CLI?

The Webpack CLI provides a set of tools to facilitate interaction with Webpack from the command line. This includes initializing configurations, running the build process, and more. The CLI makes it easier to integrate Webpack into your development workflow, allowing you to execute bundling and other tasks directly from your terminal.

### Why we use it:

Open your terminal and create a new directory for your project, then navigate into it:

```bash
mkdir webpack-demo
cd webpack-demo
```

Initialize a new npm project:

```bash
npm init -y
```

Create an HTML file for your app without Webpack. This example demonstrates what happens when you try to use a Lodash method without Webpack:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Simple App Without Webpack</title>
  </head>
  <body>
    <div id="content">Initial Text</div>
    <script src="src/index.js"></script>
    <!-- Include your JS file -->
  </body>
</html>
```

Next, create the JavaScript file mentioned in the script tag. This script will attempt to use Lodash without bundling:

```js
// src/index.js
document.getElementById('content').innerText = 'Updated Text';

// Trying to use Lodash without Webpack
import _ from 'lodash'; // This will cause an error since Lodash isn't installed or bundled
// Spend some time trying to link to lodash manually by moving into the node_modules and show what happens when you hit
const newText = _.toUpper('some text');
document.getElementById('content').innerText = newText;
```

Now, open the HTML file in a browser. This should produce an error because the code imports Lodash, but without Webpack, the dependencies are not bundled. The result is a "Module not found" error or a similar message indicating a missing import. This illustrates the problem of not using a module bundler like Webpack.

#### Installing Webpack and Webpack CLI

Run the following command in your terminal to install both Webpack and the Webpack CLI as development dependencies:

```bash
npm install --save-dev webpack webpack-cli
```

- **Development Dependencies**: We install these as development dependencies (`--save-dev`) because they are only needed during the development process, not when your application is running in production.

This installation equips your project with the necessary tools to start bundling your assets with Webpack. As we progress, you'll see how these tools work together to streamline and optimize your development process.

- Take a moment to open the [Webpack CLI Documentation](https://webpack.js.org/api/cli/) to understand the available commands and options. It's helpful to know what tools are at your disposal as you start to integrate Webpack into your projects.

### Step 3: Create Your Project Structure

Inside your project directory, create a simple file structure:

- The `src` directory will contain our source code.
- The `dist` directory will be used to output our bundled files.

```plaintext
webpack-demo/
|- /src
   |- index.js
|- /dist
   |- index.html
```

### Step 4: Add a Basic JavaScript File

In `src/index.js`, add some simple JavaScript:

```js
// src/index.js
console.log('Hello, Webpack!');
```

### Step 5: Bundle Your JavaScript

To bundle your JavaScript file using Webpack, run:

```bash
npx webpack
```

Webpack will automatically look for `src/index.js` as the entry point and output the bundle in `dist/main.js`.

### Step 6: Create an HTML File

Create `index.html` in the `dist` directory and include the bundled JavaScript file:

```html
<!-- dist/index.html -->
<!DOCTYPE html>
<html>
  <head>
    <title>Webpack Demo</title>
  </head>
  <body>
    <script src="main.js"></script>
  </body>
</html>
```

Open `dist/index.html` in your browser to see the output of your JavaScript code.

### Step 7: Adding JavaScript Modules to Your Project

To further demonstrate Webpack's capabilities and the importance of modularity in modern web development, let's add JavaScript modules to our project. This step will help us understand how Webpack bundles multiple JavaScript files into a single output file, enhancing code organization and maintainability.

#### Creating JavaScript Modules

First, let's create a couple of JavaScript module files in the `src` directory. These modules will contain simple functions that we'll import into our main `index.js` file.

Create two new files:

- `src/sayHello.js`
- `src/sayGoodbye.js`

Add the following content to them:

```js
// src/sayHello.js
export function sayHello() {
  console.log('Hello, Webpack and modules!');
}
```

```js
// src/sayGoodbye.js
export function sayGoodbye() {
  console.log('Goodbye, see you later!');
}
```

#### Importing Modules in `index.js`

Now, modify your `src/index.js` to import and use these modules:

```js
// src/index.js
import { sayHello } from './sayHello';
import { sayGoodbye } from './sayGoodbye';

sayHello();
sayGoodbye();
```

#### Running Webpack

With our modules in place, let's bundle our project again using Webpack. Run the following command in your terminal:

```bash
npx webpack
```

Webpack will automatically process the imports, bundle your `index.js` along with the imported modules, and output the result to `dist/main.js`.

#### Verifying the Output

Open or refresh `dist/index.html` in your browser and check the developer console. You should see the messages from both of your JavaScript modules, indicating that Webpack successfully bundled them together.

### Understanding the Process

This exercise highlighted how Webpack treats JavaScript modules. By importing modules in `index.js`, we tell Webpack about the dependencies between our files. Webpack then intelligently bundles these files together, allowing us to organize our code into manageable, reusable pieces without worrying about the impact on the browser's ability to load and run our application efficiently.

### Next Steps

As we move into more complex configurations and optimizations, remember the core principles of modularity and efficiency that tools like Webpack help us achieve. In the next hour, we'll explore Webpack's configuration in more detail, setting the stage for handling CSS, images, and other assets beyond JavaScript.

### Documentation and Resources

- **Webpack Documentation**: [Official Webpack Docs](https://webpack.js.org/concepts/) are an excellent resource for understanding deeper concepts and configurations.
- **Next.js and Webpack**: If you're curious, Next.js uses Webpack under the hood for its build process. Exploring the `.next` build folder in a Next.js project can be an interesting way to see Webpack's role in a larger framework. However, for now, focus on the basics to build a strong foundation.

In the next hour, we'll explore more about Webpack's configuration options to customize the way it bundles our files.

<!--! Houe 2  -->

# Week 5, Day 1, Hour 2: Setting Up and Understanding Webpack Configuration

In this session, we'll create and dissect a Webpack configuration file (`webpack.config.js`) for our project, step by step. This configuration will define how Webpack should bundle our JavaScript and later, how it integrates CSS processing with loaders. We'll link to specific sections of the Webpack documentation to deepen our understanding and validate our setup.

## Creating the Webpack Configuration File

### Step 1: Initialize the Configuration File

Create a new file named `webpack.config.js` in the root of your project. This file will hold all our Webpack settings.

### Step 2: Define the Entry Point

Webpack's functionality kicks off from an entry point. This is essentially the starting point of your application from where Webpack begins to compile your JavaScript. Although Webpack defaults to using `./src/index.js` as the entry point, you have the flexibility to specify a different file or even multiple entry points based on your project's needs.

Here's how you define an entry point in the `webpack.config.js` file:

```js
const path = require('path');

module.exports = {
  entry: './src/index.js',
};
```

- **`entry`**: This field in the Webpack configuration specifies the path to the entry file. Webpack will use this file to start building out the internal dependency graph of your application.

#### Understanding `path` and `__dirname`

In our configuration, we use the `path` module from Node.js and a global variable called `__dirname`. These are crucial for defining paths in a cross-platform compatible way:

- **`path`**: A core Node.js module that provides utilities for working with file and directory paths. It's used to ensure your paths work correctly on different operating systems.
- **`__dirname`**: A global variable in Node.js that returns the directory name of the current module (i.e., the folder where the currently executing file resides). This helps in constructing absolute paths, which are required by certain Webpack configurations like `output.path`.

## Step 3: Setting up output

For example, when setting up the `output` configuration:

```js
output: {
  filename: 'bundle.js',
  path: path.resolve(__dirname, 'dist'),
},
```

- Here, `path.resolve(__dirname, 'dist')` creates an absolute path to the `dist` directory, ensuring Webpack correctly places the output file regardless of the environment it's run in.

- **[Webpack Entry Documentation](https://webpack.js.org/concepts/entry-points/)**: For more detailed information on configuring entry points.

Understanding how `path` and `__dirname` work is essential for configuring Webpack and other Node.js-based tools, providing you with the knowledge to set up your development environment effectively.

### Step 4: Configure Loaders

Loaders let you preprocess files as you import or load them. They are transformations applied to the source code of modules. For now, let's prepare our configuration to include a rule for CSS files, which we will use shortly:

```js
module: {
  rules: [
    {
      test: /\.css$/,
      use: ['style-loader', 'css-loader'],
    },
  ],
},
```

- **Loaders**: The `test` property identifies which file or files should be transformed. The `use` property indicates which loaders to apply.
- [Webpack Loaders Documentation](https://webpack.js.org/concepts/loaders/)

At this point, we haven't installed or configured any CSS loaders yet, but we will get to that shortly. This setup is laying the groundwork.

### Step 5: Understanding the Full Configuration

Combining the above snippets, our `webpack.config.js` should now look something like this:

```js
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader'],
      },
    ],
  },
};
```

This configuration tells Webpack to:

1. Start bundling from `./src/index.js`.
2. Output the bundled file as `bundle.js` in the `dist` directory.
3. Apply the CSS loaders to any `.css` files encountered.

### Step 6: Configure the Mode

One of Webpack's features that significantly impacts the outcome of your bundle is the `mode` configuration. By setting the mode, you can enable Webpack's built-in optimizations that are suitable for either development or production environments. This setting can drastically affect your build's performance and the size of the output file.

Webpack offers three modes: `none`, `development`, and `production`, with `production` being the default if no mode is specified. Here's how to configure it:

```js
module.exports = {
  // previous configurations...
  mode: 'development',
};
```

- **`mode: 'development'`**: This setting optimizes the build for speed and makes it easier to debug. It provides more verbose output in the console and includes helpful tools like source maps.
- **`mode: 'production'`**: When you're ready to deploy your app, switch to production mode. This enables optimizations like minification, smaller bundle sizes, and optimized assets to improve load times on your users' end.

- **`mode: 'none'`**: This option disables any of Webpack's default optimizations, giving you full control but requiring you to manually specify how you want to optimize the build.

#### Why Configuring Mode Matters

Configuring the `mode` properly is crucial because it directly influences the performance and behavior of your application. During development, you want fast build times and detailed error messages, which `development` mode provides. For production, it's all about optimizing for speed and efficiency, achievable with `production` mode.

#### Switching Between Modes

For real-world projects, it's common to have separate configuration files for development and production or to dynamically set the mode based on environment variables. This allows developers to easily switch contexts and ensures that the correct optimizations are applied at the right time.

```js
const mode =
  process.env.NODE_ENV === 'production' ? 'production' : 'development';

module.exports = {
  // previous configurations...
  mode,
};
```

- **[Webpack Mode Documentation](https://webpack.js.org/configuration/mode/)**: For an in-depth understanding of what optimizations are applied in each mode.

Configuring the `mode` is a simple yet powerful way to optimize your project. Remember to review the Webpack documentation to fully leverage the optimizations each mode offers.

### Exploring the Docs

As we proceed, it's beneficial to keep the Webpack documentation handy:

- For a broad understanding, consult the [Concepts](https://webpack.js.org/concepts/) section.
- For specifics on configuration, see the [Configuration](https://webpack.js.org/configuration/) guide.

### Next Steps

Now that we have a basic understanding of a Webpack configuration file and its core components, we'll move on to installing the necessary loaders for handling CSS. This will involve modifying our project setup and `webpack.config.js` to ensure Webpack can process CSS files alongside JavaScript.

Remember, the goal of this session is not just to write a configuration file, but to understand each part of it. The Webpack documentation is a valuable resource as you learn and build more complex configurations.
