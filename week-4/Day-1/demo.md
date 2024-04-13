# Week 4, Day 1, Hour 1: Introduction to Jest and Unit Testing in Node.js

Welcome to the first hour of Week 4, where we dive into the basics of unit testing with Jest in a Node.js environment. This session is crafted for developers who are new to testing, aiming to demystify the concept of unit testing and introduce Jest as a friendly and powerful testing framework.

## What is Unit Testing?

Unit testing involves testing individual units or components of a software application. The goal is to validate that each part performs as expected. A "unit" typically refers to the smallest testable part of an application, like a function or a class method.

### Why Unit Testing?

- **Reliability**: Ensures that your code works correctly under various scenarios.
- **Refactoring Confidence**: Makes the codebase safer to refactor, knowing that tests will catch unexpected changes.
- **Documentation**: Serves as documentation for your code. Tests describe what your application does and how it behaves.

## Introduction to Jest

Jest is a delightful JavaScript Testing Framework with a focus on simplicity. It's used by companies like Facebook to test their JavaScript code, including Node.js applications.

### Key Features of Jest

- **Zero Configuration**: Jest is designed to work out of the box, with minimal setup.
- **Snapshot Testing**: Allows you to test your UI without manually writing tests for each element.
- **Built-in Coverage Reports**: Generates coverage reports to see how much of your code is covered by tests.

## Installing Jest and Configuring a Node.js Project

To get started with Jest in a Node.js project, you first need to install Jest as a development dependency.

```bash
npm install --save-dev jest
```

After installing Jest, add a test script to your `package.json`:

```json
"scripts": {
  "test": "jest"
}
```

This script enables you to run your tests using `npm test` from the terminal.

## Basic Structure of a Jest Test

A Jest test file typically contains one or more test suites, which in turn include one or more tests. The basic structure involves `describe` and `it` blocks.

- **`describe` Block**: Used to group together similar tests.
- **`it` Block**: Contains the actual test.
- **`expect` Function**: Used to make an assertion about a certain condition in the test.

### Example Test

Let's write a simple test to check if a function returns the expected output:

```js
// sum.js
function sum(a, b) {
  return a + b;
}
module.exports = sum;
```

Create a test file named `sum.test.js`:

```js
const sum = require('./sum');

describe('sum function', () => {
  it('adds 1 + 2 to equal 3', () => {
    expect(sum(1, 2)).toBe(3);
  });
});
```

Running `npm test` will execute this test, verifying that our `sum` function behaves as expected.

## Conclusion

This session introduced you to the basics of unit testing and Jest. By understanding the significance of unit testing and learning how to set up Jest in a Node.js project, you're well on your way to incorporating testing into your development workflow. Keep everything simple and straightforward, and remember, the goal is to build confidence in testing as a fundamental aspect of software development.

<!--! Hour 2 -->

## Week 4, Day 1, Hour 2: Writing Your First Tests with Jest

After familiarizing ourselves with the basics of Jest and the importance of unit testing, this hour is dedicated to putting theory into practice. We'll be writing our first tests in Jest, focusing on testing simple JavaScript functions. This hands-on approach aims to solidify your understanding of Jest's testing syntax and the concept of assertions.

## Writing Your First Jest Tests

Testing with Jest revolves around the idea of writing test cases that verify the behavior of your code. We'll start by testing some basic JavaScript functions to grasp the core concepts of assertions and test matching.

### Testing a Simple Function

Let's consider a simple JavaScript function that performs string manipulation—specifically, a function that capitalizes the first letter of a string.

1. **Create the Function**:

   ```js
   // stringFunctions.js
   function capitalize(string) {
     return string.charAt(0).toUpperCase() + string.slice(1);
   }

   module.exports = { capitalize };
   ```

2. **Write the Test**:

   Create a test file named `stringFunctions.test.js`:

   ```js
   const { capitalize } = require('./stringFunctions');

   describe('capitalize function', () => {
     it('capitalizes the first letter of a string', () => {
       expect(capitalize('jest')).toBe('Jest');
     });
   });
   ```

This test checks if the `capitalize` function correctly transforms the first letter of a given string to uppercase. Running `npm test` will execute this test.

### Understanding Assertions

In the example above, `expect(capitalize('jest')).toBe('Jest');` is an assertion. It asserts that the outcome of `capitalize('jest')` should be `'Jest'`. Jest provides a range of matchers that you can use to test different things:

- `.toBe()` checks for exact equality.
- `.toEqual()` is used for checking the equality of object values.
- There are many more matchers for different use cases.

## Best Practices for Writing Tests

- **Descriptive Test Names**: Use clear, descriptive names for your test cases to make them understandable.
- **One Assertion Per Test**: Ideally, keep to one assertion per test to make it clear what aspect of the function you're testing.
- **Arrange-Act-Assert Pattern**: Structure your tests in three stages: setup (arrange), executing the function to be tested (act), and asserting the results (assert).

## Conclusion

This session provided a practical introduction to writing tests in Jest, focusing on simple JavaScript functions. By creating a test case for a string manipulation function and understanding the basics of assertions, you're developing essential skills for test-driven development. Remember, the key to effective testing is clarity and specificity in what each test is meant to verify.
