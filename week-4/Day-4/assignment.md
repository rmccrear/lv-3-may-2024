# Assignment: Jest Assignment 4

## Objective

Enhance your Jest testing skills by focusing on Next.js components. This assignment requires you to write tests for two specific components, ensuring they render correctly and interact as expected within a Next.js application. By completing this task, you'll gain hands-on experience with testing in the context of a modern React framework.

## Instructions

### Part 1: Project Setup

1. **Create a Next.js Application**:

   - Use `create-next-app` to generate a new Next.js project.

2. **Install Dependencies**:

   - Install Jest and React Testing Library with `npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom`.

3. **Configure Jest for Next.js**:
   - Create `jest.config.js` in the project root with the provided settings from the demo.
   - Add `jest.setup.js` as specified, importing `@testing-library/jest-dom`.

### Part 2: Component Implementation and Testing

1. **WelcomeMessage Component**:

   - Implement `WelcomeMessage.js` in the `components` directory, rendering a paragraph with a message passed via props.
   - Write a test in `WelcomeMessage.test.js` under `components/__tests__` to verify that the component correctly displays the message.

2. **ToggleText Component**:
   - Create `ToggleText.js` in the `components` directory. This component should include a button that toggles the visibility of a text message on click, utilizing the `useState` hook.
   - In `ToggleText.test.js`, write tests to ensure:
     - The text is not visible initially.
     - Clicking the button makes the text visible.

### Part 3: Test Execution and Validation

- Run your tests using `npm test` to ensure they pass based on the criteria described.
- Verify that each component behaves as expected, both initially and after user interaction.

## Submission

- **Repository Creation**: Push your completed project to a GitHub repository named `jest-nextjs-assignment-4`.
- **Documentation**: Update the `README.md` with setup instructions and a brief description of your testing approach.
- **Submit the URL of your GitHub repository**.

## Rubric

### Jest and React Testing Library Integration - 5 points

- **Complete (5 pts)**: Jest and React Testing Library are correctly configured for Next.js, allowing tests to run smoothly.
- **Partial (3 pts)**: Minor issues in configuration that do not significantly impact test execution.
- **Limited (1 pt)**: Significant misconfigurations preventing tests from running correctly.

### WelcomeMessage Component Testing - 5 points

- **Complete (5 pts)**: Tests comprehensively verify that `WelcomeMessage` renders the prop message accurately.
- **Partial (3 pts)**: Tests cover basic rendering but miss edge cases or more detailed assertions.
- **Limited (1 pt)**: Tests are incorrect, missing, or fail to accurately validate component rendering.

### ToggleText Component Interaction Testing - 5 points

- **Complete (5 pts)**: Interaction tests accurately assess the visibility toggle feature, including initial state and post-click behavior.
- **Partial (3 pts)**: Some aspects of interaction are tested, but the coverage is incomplete or lacks precision.
- **Limited (1 pt)**: Interaction tests are poorly implemented, missing, or fail to capture the component's behavior correctly.

### Code Quality and Clarity - 5 points

- **Complete (5 pts)**: Code is well-structured, clean, and follows best practices for Next.js and React development.
- **Partial (3 pts)**: Generally good code quality with minor areas for improvement in structure or practices.
- **Limited (1 pt)**: Code is difficult to follow, poorly organized, or deviates significantly from recommended practices.

### Documentation and README - 5 points

- **Complete (5 pts)**: `README.md` clearly explains project setup, test running instructions, and the rationale behind test cases.
- **Partial (3 pts)**: `README.md` provides basic setup and testing information but lacks detail or clarity.
- **Limited (1 pt)**: `README.md` is missing, incomplete, or fails to provide necessary setup and testing guidance.
