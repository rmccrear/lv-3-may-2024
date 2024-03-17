# Assignment: Jest Assignment 1

## Objective

Gain hands-on experience with Jest by setting up a Node.js environment for unit testing. Create specific utility functions, write tests to validate their functionality, and ensure your code adheres to best practices in testing.

## Instructions

### Part 1: Create and Clone Your GitHub Repository

1. **Create a New GitHub Repository**:

   - Name your repository `jest-testing-basics`.
   - Initialize it with a `.gitignore` for Node.js and a README.md.

2. **Clone Your Repository**:
   - Navigate to the cloned repository's directory to begin your project setup.

### Part 2: Setup and Configuration

1. **Initialize a Node.js Project**:

   - Within your project directory, run `npm init -y` to generate a `package.json` file.

2. **Install Jest**:
   - Add Jest as a development dependency with `npm install --save-dev jest`.
   - In your `package.json`, add a test script to run Jest:
     ```json
     "scripts": {
       "test": "jest"
     }
     ```

### Part 3: Writing Tests

1. **Utility Functions Implementation**:

   - Create a file `utils.js` and implement two functions:
     - `multiply(a, b)`: Returns the multiplication of `a` and `b`.
     - `isPrime(number)`: Checks if `number` is a prime number.

2. **Testing**:
   - Write tests for both functions in `utils.test.js`, covering expected behavior and edge cases. For `multiply`, test normal multiplication, multiplying by zero, and negative numbers. For `isPrime`, test prime numbers, non-prime numbers, and negative input.

### Part 4: Documentation

- **Update README.md**:
  - Document the setup process, how to run tests, and a brief explanation of each utility function and its tests.

## Submission

- **GitHub Repository**: Submit the URL of your GitHub repository. Make sure it includes all necessary files to run the tests, the updated README.md, and is set to public.

## Rubric

### Jest Setup and Configuration - 5 points

- **Complete (5 pts)**: Jest is correctly installed, and `package.json` is configured with a test script.
- **Partial (3 pts)**: Jest is installed with minor issues in configuration.
- **Limited (0 pts)**: Incorrect Jest setup or configuration issues preventing test execution.

### Function Implementation - 5 points

- **Complete (5 pts)**: Both `multiply` and `isPrime` functions are implemented correctly and work as expected.
- **Partial (3 pts)**: Minor issues in one of the function implementations.
- **Limited (0 pts)**: Significant implementation errors or both functions not working as expected.

### Test Coverage and Quality - 5 points

- **Complete (5 pts)**: Comprehensive test coverage for all specified cases, demonstrating understanding of testing principles.
- **Partial (3 pts)**: Adequate test coverage with minor gaps or some failing tests.
- **Limited (0 pts)**: Poor test coverage, significant gaps in testing, or most tests fail.

### Code Quality - 5 points

- **Complete (5 pts)**: Code is clean, well-organized, and follows best practices.
- **Partial (3 pts)**: Generally good code quality with minor areas for improvement.
- **Limited (0 pts)**: Code is hard to read, poorly organized, or does not follow best practices.

### Documentation - 5 points

- **Complete (5 pts)**: The README.md thoroughly documents the project setup, how to run tests, and the logic behind the utility functions and their tests.
- **Partial (3 pts)**: The README.md covers the basics but lacks detail or clarity in some sections.
- **Limited (0 pts)**: Inadequate documentation in the README.md or critical sections missing.
