# Week 4, Day 2, Hour 1: Deepening Understanding of Jest with More Complex Tests

Building on the foundational knowledge of Jest we established on Day 1, today's focus shifts towards writing more complex tests and introducing the testing of asynchronous code in Node.js. This hour is crucial for understanding how Jest handles asynchronous operations, a common aspect of real-world applications.

## Expanding Test Complexity with Jest

As we progress, it's important to challenge our understanding by testing more complex scenarios. This involves not just simple input-output functions but those that involve conditional logic, loops, and even error handling.

### Example: Testing a Function with Conditional Logic

Consider a function that categorizes input based on predefined rules:

```js
// categorizeInput.js
function categorizeInput(value) {
  if (value > 10) {
    return 'large';
  } else if (value <= 10 && value >= 1) {
    return 'medium';
  } else {
    return 'small';
  }
}

module.exports = categorizeInput;
```

A test for this function would cover all possible outcomes:

```js
// categorizeInput.test.js
const categorizeInput = require('./categorizeInput');

describe('categorizeInput function', () => {
  it('returns "large" for values greater than 10', () => {
    expect(categorizeInput(11)).toBe('large');
  });

  it('returns "medium" for values between 1 and 10', () => {
    expect(categorizeInput(5)).toBe('medium');
  });

  it('returns "small" for values less than 1', () => {
    expect(categorizeInput(0)).toBe('small');
  });
});
```

## Testing Asynchronous Code: Callbacks, Promises, and async/await

Asynchronous code is a staple in JavaScript, especially in Node.js for database operations, API calls, and file handling. Jest provides a simple API for testing code that executes asynchronously.

### Callbacks

To test a function that uses a callback, Jest needs to know when to finish the test. This is done by calling a `done` parameter that Jest provides to your test function.

```js
// asyncOperation.js
function fetchData(callback) {
  setTimeout(() => {
    callback('peanut butter');
  }, 1000);
}

module.exports = fetchData;
```

```js
// asyncOperation.test.js
const fetchData = require('./asyncOperation');

test('the data is peanut butter', (done) => {
  function callback(data) {
    expect(data).toBe('peanut butter');
    done();
  }

  fetchData(callback);
});
```

### Promises

For promises, return the promise from your test, and Jest will wait for that promise to resolve before finishing the test.

```js
// fetchData.js
function fetchData() {
  return new Promise((resolve, reject) => {
    resolve('peanut butter');
  });
}

module.exports = fetchData;
```

```js
// fetchData.test.js
const fetchData = require('./fetchData');

test('the data is peanut butter', () => {
  return fetchData().then((data) => {
    expect(data).toBe('peanut butter');
  });
});
```

### async/await

Jest supports `async/await` for testing asynchronous code, which makes your tests cleaner and easier to read.

```js
// fetchData.test.js
const fetchData = require('./fetchData');

test('the data is peanut butter', async () => {
  const data = await fetchData();
  expect(data).toBe('peanut butter');
});
```

## Conclusion

This hour has expanded your testing capabilities with Jest by introducing the testing of more complex functions and asynchronous code. Understanding how to effectively test asynchronous operations is key to building robust Node.js applications. Remember, the goal is to ensure your application behaves as expected, even in asynchronous scenarios.

<!-- ! Hour 2 -->

# Week 4, Day 2, Hour 2: Introduction to Mocking with Jest

In this hour, we dive into a critical aspect of testing complex applications: mocking. Mocking is a powerful technique in unit testing that allows you to isolate the piece of code being tested by replacing its dependencies with mock implementations. This is particularly useful for simplifying tests, speeding up test execution, and focusing on the functionality being tested without worrying about the external dependencies.

## Why Mocking?

- **Isolation**: Mocking allows you to isolate the unit of code you're testing, ensuring that tests are not affected by external factors such as network requests, database connections, or other modules.
- **Control**: It gives you control over the behavior of dependencies within your tests, allowing you to simulate different scenarios.
- **Simplicity**: By using mocks, you can simplify the setup of your tests, making them faster and more focused.

## Introduction to Jest's Mocking Capabilities

Jest comes with built-in support for mocking, making it straightforward to implement mocks in your tests.

### Mocking Modules

Suppose you have a module that fetches data from an API. You can mock this module to return a fixed response every time it's called, ensuring your tests run quickly and consistently.

```js
// api.js
const fetchData = () => {
  // Imagine this function fetches data from an external API
};

module.exports = { fetchData };
```

To mock this module in your test:

```js
// __tests__/api.test.js
jest.mock('../api'); // Path to the module being mocked

const { fetchData } = require('../api');

// Implementing a mock function
fetchData.mockImplementation(() => Promise.resolve('mock data')); // keeps track of how many times the function was called, and with what paramters

test('fetches mock data', async () => {
  const data = await fetchData("a random string");
  expect(data).toBe('mock data');
  // pass reference to the mocked function to see what it was called with
  expect(fetchData).toHaveBeenCalledWith("a random string")
});
```

### Mocking Functions

Jest also allows you to mock individual functions. This is useful when you want to test how your code reacts to different return values or effects caused by those functions.

```js
// utils.js
const calculateSomething = () => {
  // Some complex calculation
};
module.exports = { calculateSomething };
```

Mocking `calculateSomething` function in a test:

```js
// __tests__/utils.test.js
const { calculateSomething } = require('../utils');

jest.mock('../utils', () => ({
  calculateSomething: jest.fn(() => 42),
}));

test('calculateSomething returns 42', () => {
  expect(calculateSomething()).toBe(42);
});
```

## Best Practices for Organizing Tests with Mocks

- **Clear Mocks**: Use `beforeEach` or `afterEach` to clear or reset mocks to ensure they don't affect other tests.
- **Document Mocks**: Clearly document why and what you're mocking to make your tests understandable.
- **Keep It Real**: While mocking is powerful, try to keep your mocks as close to the real implementations as possible to ensure your tests accurately reflect real-world scenarios.

## Conclusion

This session introduced the concept of mocking in Jest, a fundamental technique for isolating units of code, controlling dependencies, and simplifying tests. As you grow more comfortable with mocking, you'll find it an invaluable tool in your testing arsenal, enabling you to write more focused, reliable, and maintainable tests.
