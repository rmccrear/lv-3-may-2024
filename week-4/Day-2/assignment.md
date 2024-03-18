# Assignment: Jest Assignment 2

## Objective

Deepen your proficiency with Jest by tackling complex testing scenarios, including asynchronous functions and mocking external dependencies. This assignment will guide you through specific tasks to enhance your understanding of Jest's capabilities in testing real-world applications.

## Instructions

### Part 1: GitHub Repository Setup

1. **Create Repository**:

   - On GitHub, create a repository named `advanced-jest-features`.
   - Initialize it with a `.gitignore` for Node.js and a basic README.md.

2. **Local Environment Setup**:
   - Clone `advanced-jest-features` to your local machine.
   - Run `npm init -y` to generate a `package.json`.
   - Install Jest using `npm install --save-dev jest`.
   - Configure a test script in `package.json`:
     ```json
     "scripts": {
       "test": "jest"
     }
     ```

### Part 2: Asynchronous Testing

1. **Function Implementation**:

   - In `dataFetcher.js`, implement `fetchData(url)` that simulates fetching data by returning a promise that resolves to `"Fetched data from ${url}"` after a 1-second delay.

2. **Write Asynchronous Tests**:
   - Create `dataFetcher.test.js`.
   - Test `fetchData` using `.then` for a URL "http://example.com".
   - Write another test using `async/await` for the same URL.

### Part 3: Introduction to Mocking

1. **Mocking Setup**:

   - In `emailService.js`, write a function `sendEmail(to, subject, body)` that simulates sending an email.
   - This function simply returns `"Email sent to ${to}"`.

2. **Mocking Tests**:
   - In `emailService.test.js`, mock `sendEmail` to test without actually sending emails.
   - Verify that `sendEmail` is called with correct parameters when you invoke it in your test.

### Part 4: Submission and Documentation

- **Update README.md**:
  - Explain how to run tests.
  - Describe the purpose of each function and the rationale behind your test cases, including how mocking is employed.

## Submission

- Push all changes to your `advanced-jest-features` repository.
- Submit the URL of your GitHub repository.

## Rubric

### Asynchronous Function Testing - 5 points

- **Complete (5 pts)**: Both `.then` and `async/await` tests for `fetchData` are correctly implemented and passing.
- **Partial (3 pts)**: One of the tests for `fetchData` is missing or incorrect, but the other is correctly implemented.
- **Limited (1 pt)**: Both tests for `fetchData` are incorrectly implemented or missing.

### Mock Function Implementation - 5 points

- **Complete (5 pts)**: `sendEmail` is correctly mocked; tests verify it is called with the correct parameters.
- **Partial (3 pts)**: The mock of `sendEmail` is implemented, but tests partially verify it is called with correct parameters.
- **Limited (1 pt)**: The mock of `sendEmail` is incorrect or missing; tests do not verify correct parameters.

### Test Coverage and Quality - 5 points

- **Complete (5 pts)**: Tests cover all specified scenarios with clear, concise, and correct assertions.
- **Partial (3 pts)**: Test coverage is adequate, but some scenarios are not tested or assertions are not entirely correct.
- **Limited (1 pt)**: Poor test coverage; many scenarios are untested or assertions are incorrect.

### Code Quality and Clarity - 5 points

- **Complete (5 pts)**: Code and tests are exceptionally well-written, organized, and easy to understand.
- **Partial (3 pts)**: Minor issues with code organization or clarity, but generally well-written.
- **Limited (1 pt)**: Code or tests are poorly organized, difficult to understand, or have significant quality issues.

### Documentation in README.md - 5 points

- **Complete (5 pts)**: README.md thoroughly documents how to run tests, the purpose of each function, test rationale, and the use of mocking.
- **Partial (3 pts)**: README.md is mostly complete but lacks some details on running tests, function purposes, or the rationale behind tests.
- **Limited (1 pt)**: README.md is incomplete, missing significant information on how to run tests, function purposes, or the rationale behind tests.
