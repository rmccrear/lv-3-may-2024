# Week 4, Day 4, Hour 1: Basic Unit Testing in Next.js with Jest

Welcome to the introduction of unit testing within a Next.js project, focusing on client-side code. Today, we'll cover the essentials of setting up Jest for Next.js and crafting simple tests to ensure components render correctly and display the intended content. This session aims to translate our existing Jest knowledge into the context of a React-based framework like Next.js, emphasizing testing components in isolation and verifying their output.

## Setting Up Jest for Next.js

To begin unit testing in Next.js, we first set up Jest, a delightful testing framework that simplifies the testing process.

### Installation

Ensure Jest and necessary testing libraries are added to your project:

```bash
npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom
```

### Configure Jest

Create a `jest.config.js` file in your project root to tailor Jest's behavior for a React environment:

```js
module.exports = {
  testEnvironment: 'jsdom',
  setupFilesAfterEnv: ['<rootDir>/jest.setup.js'],
};
```

And in `jest.setup.js`, include global configurations and assertions enhancements:

```js
import '@testing-library/jest-dom';
```

## Writing Basic Tests

Our focus will be on verifying that components render without errors and that their content matches expectations. This is crucial for ensuring user-facing features work correctly.

### Example: Testing Text Content

Consider a component that displays a greeting message. We want to test that the component correctly renders the message passed via props.

First, the component (`Greeting.js`):

```jsx
function Greeting({ message }) {
  return <div>{message}</div>;
}

export default Greeting;
```

Next, the test (`Greeting.test.js`):

```js
import { render, screen } from '@testing-library/react';
import Greeting from '../components/Greeting';

describe('Greeting Component', () => {
  it('displays the correct greeting message', () => {
    render(<Greeting message="Hello, Next.js!" />);
    const greetingElement = screen.getByText('Hello, Next.js!');
    expect(greetingElement).toBeInTheDocument();
  });
});
```

This test ensures that the `Greeting` component renders the text "Hello, Next.js!" when provided with that message prop.

### Avoiding "undefined" Text

A common pitfall in rendering dynamic content is accidentally displaying "undefined" or incorrect text. Our testing strategy helps catch such errors by explicitly checking the rendered content against expected values.

## Conclusion

Integrating Jest into a Next.js project and writing basic unit tests for client-side components are foundational skills for ensuring the quality of your web applications. By focusing on simple, targeted tests, we can verify that our components behave as expected, providing a reliable and user-friendly experience. As we progress, we'll explore more advanced testing techniques tailored to Next.js's capabilities.

<!--! Hour 2  -->
