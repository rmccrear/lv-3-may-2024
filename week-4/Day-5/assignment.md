# Assignment: Jest Assignment 5

## Objective

Transition from unit testing to the broader scope of integration testing within a Next.js application. This assignment encourages you to apply the foundational testing knowledge gained this week to a slightly more complex scenario, focusing on the interaction between components and API calls.

## Instructions

### Part 1: Project Setup

1. **Create a New Next.js Application**:

   - Use `npx create-next-app` to initialize your project.
   - Navigate to your project directory.

2. **Install Testing Dependencies**:

   - Execute `npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom` to add necessary libraries for testing.

3. **Jest Configuration**:
   - Set up Jest for your Next.js project by creating a `jest.config.js` with the given configuration from the demo.
   - Include a `jest.setup.js` file to import `@testing-library/jest-dom`.

### Part 2: Integration Test Implementation

1. **User Signup Component**:

   - Implement a `UserSignup.js` component in the `components` directory. This component should include a form allowing users to sign up with their name and email.
   - Simulate a backend API call within the component for submitting the form data.

2. **Integration Test for User Signup**:
   - Write a test in `__tests__/UserSignup.test.js` to simulate a user filling out the signup form and submitting it.
   - Mock the API call to verify the component handles the submission correctly and displays a success message upon completion.

### Part 3: Advanced Testing Scenario

1. **Navigation Flow Test**:
   - Create a simple navigation component `components/Navbar.js` that links to the `UserSignup` page and a `Home` page.
   - In `__tests__/NavigationFlow.test.js`, write an integration test that simulates navigating from the `Home` page to the `UserSignup` page and verifies the navigation works as expected.
