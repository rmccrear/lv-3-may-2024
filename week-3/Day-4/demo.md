# Week 3, Day 4: Advanced Testing with Jest

Welcome to Day 4 of Week 3! Today, we will cover advanced testing concepts with Jest, focusing on simple unit testing and testing client-side JavaScript in a Next.js environment.

## Objectives

- Understand how to write simple unit tests with Jest.
- Learn how to test client-side JavaScript in a Next.js project.
- Get a high-level understanding of testing best practices.

## Instructor Notes

### Simple Unit Testing with Jest

- Explain what unit testing is and why it is important.
- Demonstrate how to write and run simple unit tests using Jest.

### Testing Client-Side JavaScript in Next.js

- Provide a brief overview of how to set up Jest in a Next.js project.
- Demonstrate how to write and run tests for client-side JavaScript in a Next.js project.

## Hourly Breakdown

### Hour 1: Simple Unit Testing with Jest

- **Objectives**:
  - Understand the basics of unit testing.
  - Write and run simple unit tests using Jest.
- **Teaching Ideas**:

  - Explain unit testing:
    - Unit testing involves testing individual units of code to ensure they work as expected.
  - Benefits of unit testing:
    - Helps catch bugs early.
    - Ensures code behaves as expected.
  - Write a simple unit test:

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

### Hour 2: Testing Client-Side JavaScript in Next.js

- **Objectives**:
  - Learn how to set up and use Jest in a Next.js project.
  - Write and run tests for client-side JavaScript in Next.js.
- **Teaching Ideas**:

  - Setting up Jest in a Next.js project:

    ```bash
    npx create-next-app jest-next-demo
    cd jest-next-demo
    npm install --save-dev jest @testing-library/react @testing-library/jest-dom babel-jest
    ```

  - Add the following to `package.json` to configure Jest:

    ```json
    "jest": {
        "testEnvironment": "jsdom",
        "setupFilesAfterEnv": ["<rootDir>/jest.setup.js"]
    },
    "scripts": {
        "test": "jest"
    }
    ```

  - Create a `jest.setup.js` file to configure Testing Library:

    ```js
    import '@testing-library/jest-dom';
    ```

  - Write a simple component and test:

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

  - Run the tests:
    ```bash
    npm test
    ```

### Practical Exercise

- Have students follow along and set up Jest in their own Next.js projects.
- Assist students in writing and running their first unit tests.
- Encourage students to test different components and client-side JavaScript logic.

## Code Snippets

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
# Setting up Jest in a Next.js project
npx create-next-app jest-next-demo
cd jest-next-demo
npm install --save-dev jest @testing-library/react @testing-library/jest-dom babel-jest
```

```json
// Add Jest configuration and test script to package.json
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
# Run the tests
npm test
```

## Conclusion

- Summarize the key points covered:
  - Unit testing ensures individual units of code work as expected.
  - Jest is a powerful tool for writing and running JavaScript tests.
  - Setting up Jest in a Next.js project allows for testing client-side JavaScript.
- Encourage students to explore more advanced testing features and best practices in their own time.
