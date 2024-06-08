# Week 3, Day 5: Review of Webpack, Babel, and Jest

Welcome to Day 5 of Week 3! Today, we will review the key concepts and skills covered throughout the week, focusing on Webpack, Babel, and Jest. This will reinforce your understanding and ensure you are comfortable with these tools.

## Objectives

- Review the key concepts and skills related to Webpack.
- Review the key concepts and skills related to Babel.
- Review the key concepts and skills related to Jest.
- Provide a comprehensive understanding of how these tools work together in modern web development.

## Instructor Notes

### Review of Webpack

- Recap the purpose and benefits of using Webpack.
- Review setting up a basic Webpack project and configuring it.
- Reinforce how to bundle JavaScript files with Webpack.

### Review of Babel

- Recap the purpose and benefits of using Babel.
- Review setting up Babel in a Webpack project.
- Reinforce how Babel transpiles modern JavaScript to ensure compatibility with older browsers.

### Review of Jest

- Recap the purpose and benefits of using Jest.
- Review setting up Jest in a project.
- Reinforce how to write and run basic unit tests with Jest.

## Hourly Breakdown

### Hour 1: Review of Webpack and Babel

- **Objectives**:
  - Reinforce the key concepts and skills related to Webpack and Babel.
- **Teaching Ideas**:

  - Review Webpack:

    - Purpose: Module bundler for JavaScript applications.
    - Benefits: Efficient module bundling, support for various asset types.
    - Setting up a project:
      ```bash
      mkdir webpack-demo
      cd webpack-demo
      npm init -y
      npm install --save-dev webpack webpack-cli
      ```
    - Basic configuration:

      ```js
      const path = require('path');

      module.exports = {
        entry: './src/index.js',
        output: {
          filename: 'bundle.js',
          path: path.resolve(__dirname, 'dist'),
        },
      };
      ```

    - Demonstrating JavaScript file bundling:

      ```js
      function component() {
        const element = document.createElement('div');
        element.innerHTML = 'Hello, Webpack!';
        return element;
      }

      document.body.appendChild(component());
      ```

      ```bash
      npm run build
      ```

  - Review Babel:

    - Purpose: JavaScript compiler for using next-generation JavaScript, today.
    - Benefits: Ensures compatibility with older browsers.
    - Setting up Babel in a Webpack project:

      ```bash
      npm install --save-dev babel-loader @babel/core @babel/preset-env
      ```

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
              test: /\.js$/,
              exclude: /node_modules/,
              use: {
                loader: 'babel-loader',
                options: {
                  presets: ['@babel/preset-env'],
                },
              },
            },
          ],
        },
      };
      ```

    - Demonstrating JavaScript transpilation:

      ```js
      const arrowFunction = () => {
        console.log('Hello, Babel!');
      };

      arrowFunction();
      ```

      ```bash
      npm run build
      ```

### Hour 2: Review of Jest

- **Objectives**:
  - Reinforce the key concepts and skills related to Jest.
- **Teaching Ideas**:

  - Review Jest:

    - Purpose: JavaScript testing framework for ensuring code correctness.
    - Benefits: Simple setup, comprehensive testing features.
    - Setting up Jest:
      ```bash
      npm install --save-dev jest
      ```
      ```json
      "scripts": {
          "test": "jest"
      }
      ```
    - Writing and running basic unit tests:

      ```js
      // src/sum.js
      function sum(a, b) {
        return a + b;
      }

      module.exports = sum;
      ```

      ```js
      // src/sum.test.js
      const sum = require('./sum');

      test('adds 1 + 2 to equal 3', () => {
        expect(sum(1, 2)).toBe(3);
      });
      ```

      ```bash
      npm test
      ```

    - Testing client-side JavaScript in Next.js:

      ```bash
      npx create-next-app jest-next-demo
      cd jest-next-demo
      npm install --save-dev jest @testing-library/react @testing-library/jest-dom babel-jest
      ```

      ```json
      "jest": {
          "testEnvironment": "jsdom",
          "setupFilesAfterEnv": ["<rootDir>/jest.setup.js"]
      },
      "scripts": {
          "test": "jest"
      }
      ```

      ```js
      // jest.setup.js
      import '@testing-library/jest-dom';
      ```

      ```js
      // components/Greeting.js
      function Greeting({ name }) {
        return <h1>Hello, {name}!</h1>;
      }

      export default Greeting;
      ```

      ```js
      // components/Greeting.test.js
      import { render, screen } from '@testing-library/react';
      import Greeting from './Greeting';

      test('renders greeting with name', () => {
        render(<Greeting name="John" />);
        expect(screen.getByText('Hello, John!')).toBeInTheDocument();
      });
      ```

      ```bash
      npm test
      ```

### Practical Exercise

- Have students review their own projects and ensure they are comfortable with the setup and usage of Webpack, Babel, and Jest.
- Encourage students to create a small project that integrates all three tools, reinforcing their understanding.

## Code Snippets

```bash
# Setting up a basic Webpack project
mkdir webpack-demo
cd webpack-demo
npm init -y
npm install --save-dev webpack webpack-cli
```

```js
// Basic Webpack configuration
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
};
```

```js
// Demonstrating JavaScript file bundling
function component() {
  const element = document.createElement('div');
  element.innerHTML = 'Hello, Webpack!';
  return element;
}

document.body.appendChild(component());
```

```bash
# Setting up Babel in a Webpack project
npm install --save-dev babel-loader @babel/core @babel/preset-env
```

```js
// Webpack configuration with Babel
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
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader',
          options: {
            presets: ['@babel/preset-env'],
          },
        },
      },
    ],
  },
};
```

```js
// Demonstrating JavaScript transpilation
const arrowFunction = () => {
  console.log('Hello, Babel!');
};

arrowFunction();
```

```bash
# Setting up Jest
npm install --save-dev jest
```

```json
// Adding test script to package.json
"scripts": {
    "test": "jest"
}
```

```js
// Writing a simple unit test with Jest
// src/sum.js
function sum(a, b) {
  return a + b;
}

module.exports = sum;
```

```js
// src/sum.test.js
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

```bash
# Running the test
npm test
```

```bash
# Setting up Jest in a Next.js project
npx create-next-app jest-next-demo
cd jest-next-demo
npm install --save-dev jest @testing-library/react @testing-library/jest-dom babel-jest
```

```json
// Adding Jest configuration and test script to package.json
"jest": {
    "testEnvironment": "jsdom",
    "setupFilesAfterEnv": ["<rootDir>/jest.setup.js"]
},
"scripts": {
    "test": "jest"
}
```

```js
// jest.setup.js
import '@testing-library/jest-dom';
```

```js
// Writing a simple component and test
// components/Greeting.js
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}

export default Greeting;
```

```js
// components/Greeting.test.js
import { render, screen } from '@testing-library/react';
import Greeting from './Greeting';

test('renders greeting with name', () => {
  render(<Greeting name="John" />);
  expect(screen.getByText('Hello, John!')).toBeInTheDocument();
});
```

```bash
# Running the tests
npm test
```

## Conclusion

- Summarize the key points covered:
  - Webpack, Babel, and Jest are essential tools in modern web development.
  - Each tool serves a specific purpose and integrates seamlessly into the development workflow.
  - Reviewing these tools ensures a solid understanding of their setup and usage.
- Encourage students to apply these tools in their own projects and explore advanced features.
