# Week 3, Day 3: Introduction to Jest

Welcome to Day 3 of Week 3! Today, we will introduce Jest, set up testing in a project, and demonstrate basic testing concepts.

## Objectives

- Understand the purpose and benefits of using Jest.
- Set up Jest in a project.
- Demonstrate basic testing concepts with Jest.

## Instructor Notes

### Introduction to Jest

- Explain what Jest is and why it is used in modern web development.
  - Jest is a JavaScript testing framework designed to ensure the correctness of any JavaScript codebase.
  - Benefits include a simple setup, comprehensive testing features, and excellent performance.

### Setting Up Jest in a Project

- Guide students through adding Jest to an existing project and configuring it to run tests.

### Demonstrating Basic Testing Concepts

- Show how to write and run basic tests using Jest.
- Demonstrate testing functions and modules.

## Hourly Breakdown

### Hour 1: Introduction to Jest and Setting Up Jest in a Project

- **Objectives**:
  - Understand the purpose and benefits of using Jest.
  - Set up Jest in a project.
- **Teaching Ideas**:

  - Explain Jest:
    - Jest is a testing framework for JavaScript that works out of the box for most projects.
    - Benefits of using Jest include easy setup, snapshot testing, and built-in mocking.
  - Install Jest as a development dependency:
    ```bash
    npm install --save-dev jest
    ```
  - Update `package.json` to add a test script:
    ```json
    "scripts": {
        "test": "jest"
    }
    ```
  - Create a simple JavaScript file to test:

    ```js
    // src/sum.js
    function sum(a, b) {
      return a + b;
    }

    module.exports = sum;
    ```

  - Create a test file for the JavaScript file:

    ```js
    // src/sum.test.js
    const sum = require('./sum');

    test('adds 1 + 2 to equal 3', () => {
      expect(sum(1, 2)).toBe(3);
    });
    ```

  - Run Jest to execute the test:
    ```bash
    npm test
    ```

### Hour 2: Demonstrating Basic Testing Concepts with Jest

- **Objectives**:
  - Demonstrate basic testing concepts with Jest.
- **Teaching Ideas**:

  - Write and run basic tests:

    - Example of a simple test:

      ```js
      // src/sum.test.js
      const sum = require('./sum');

      test('adds 1 + 2 to equal 3', () => {
        expect(sum(1, 2)).toBe(3);
      });
      ```

  - Test functions and modules:

    - Example of testing a function with different inputs:

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

      test('adds 2 + 2 to equal 4', () => {
        expect(sum(2, 2)).toBe(4);
      });

      test('adds -1 + 1 to equal 0', () => {
        expect(sum(-1, 1)).toBe(0);
      });
      ```

  - Explain how to use different matchers:

    - Example of using `.toEqual` for object comparison:

      ```js
      // src/object.test.js
      const data = { one: 1 };
      data['two'] = 2;

      test('object assignment', () => {
        const expected = { one: 1, two: 2 };
        expect(data).toEqual(expected);
      });
      ```

### Practical Exercise

- Have students follow along and set up Jest in their own projects.
- Assist students in writing and running their first tests.
- Encourage students to test different functions and experiment with various Jest matchers.

## Code Snippets

```bash
# Install Jest as a development dependency
npm install --save-dev jest
```

```json
// Add test script to package.json
"scripts": {
    "test": "jest"
}
```

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

test('adds 2 + 2 to equal 4', () => {
  expect(sum(2, 2)).toBe(4);
});

test('adds -1 + 1 to equal 0', () => {
  expect(sum(-1, 1)).toBe(0);
});
```

```js
// src/object.test.js
const data = { one: 1 };
data['two'] = 2;

test('object assignment', () => {
  const expected = { one: 1, two: 2 };
  expect(data).toEqual(expected);
});
```

```bash
# Run Jest to execute the tests
npm test
```

## Conclusion

- Summarize the key points covered:
  - Jest is a powerful testing framework for JavaScript.
  - Setting up Jest involves installing the package and adding a test script.
  - Jest allows for writing and running tests to ensure code correctness.
- Encourage students to explore more advanced Jest features in their own time.
