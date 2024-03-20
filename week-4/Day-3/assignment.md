# Assignment: Jest Assignment 3

## Objective

Expand your testing capabilities by integrating and testing third-party API calls in a Node.js application using Jest. This assignment focuses on creating mock functions to simulate API calls, allowing you to test your application's response to various scenarios such as successful data retrieval and error handling.

## Instructions

### Part 1: Setup Your Testing Environment

1. **Repository Creation**:

   - Create a GitHub repository named `jest-api-mock-testing`.
   - Initialize it with a `.gitignore` file for Node.js and a README.md file.

2. **Clone and Prepare**:
   - Clone the repository to your local machine.
   - Inside the project directory, run `npm init -y` to generate a `package.json` file.
   - Install Jest by running `npm install --save-dev jest`.

### Part 2: Implement and Test API Integration

1. **API Integration Function**:

   - Implement a function `getUser` in `userApi.js` that fetches user data from a placeholder API: `https://jsonplaceholder.typicode.com/users/1`.

2. **Write Tests for `getUser`**:
   - In `userApi.test.js`, write tests for the `getUser` function to simulate:
     - Successful data retrieval.
     - Error handling for network issues or user not found.

### Part 3: Mocking External API Calls

1. **Mocking Setup**:
   - Utilize Jest's mocking capabilities to intercept and mock the API calls made by `getUser`.
   - Ensure your mock simulates both success and failure scenarios effectively.

### Part 4: Error Handling and Async Testing

1. **Advanced Testing**:
   - Write tests that specifically check how your application handles and recovers from errors during API calls.
   - Use Jest's async/await support to manage asynchronous testing cleanly.

## Submission

- **Push Your Code**: Ensure all code changes, including your API integration and tests, are pushed to your `jest-api-mock-testing` repository.
- **README.md**: Update the README.md with instructions for installing dependencies, running tests, and a brief explanation of your testing approach.

## Rubric

### API Integration Implementation - 5 points

- **Complete (5 pts)**: The `getUser` function is correctly implemented, successfully fetching data from the API.
- **Partial (3 pts)**: Minor issues in the `getUser` function implementation; fetches data but with some errors.
- **Limited (0 pt)**: Significant issues with the `getUser` function; fails to fetch data correctly.

### Test Coverage and Correctness - 5 points

- **Complete (5 pts)**: Comprehensive test coverage for both success and error scenarios in API calls. All tests pass.
- **Partial (3 pts)**: Adequate test coverage; most scenarios are covered, but minor issues exist. Most tests pass.
- **Limited (0 pt)**: Insufficient test coverage; significant scenarios are missing or incorrect. Many tests fail.

### Mocking External API Calls - 5 points

- **Complete (5 pts)**: Successfully mocks external API calls, accurately simulating both success and error responses.
- **Partial (3 pts)**: Mocks external API calls with minor inaccuracies or omissions in simulating responses.
- **Limited (0 pt)**: Fails to effectively mock external API calls or simulate accurate responses.

### Async Testing Proficiency - 5 points

- **Complete (5 pts)**: Demonstrates advanced proficiency in testing asynchronous code, using async/await syntax where appropriate.
- **Partial (3 pts)**: Generally proficient in async testing, but with room for improvement in using async/await syntax effectively.
- **Limited (0 pt)**: Struggles with async testing, with significant issues in handling or understanding async/await syntax.

### Code Quality and Organization - 5 points

- **Complete (5 pts)**: Code is exceptionally well-organized, readable, and follows best practices for Node.js and Jest.
- **Partial (3 pts)**: Code is mostly well-organized and readable, with minor deviations from best practices.
- **Limited (0 pt)**: Code lacks organization, readability, or adherence to best practices.
