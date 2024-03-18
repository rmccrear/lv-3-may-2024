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

## Day 4, Hour 2: Writing Tests for Next.js Components

In this hour, we'll dive deeper into testing Next.js components using Jest and the React Testing Library. We aim to ensure that our components render correctly and respond to user interactions as expected. This session covers testing a simple component and introduces the concepts of testing hooks and event handling in React components.

### Step 1: Testing Component Rendering

We'll start by testing a simple component to ensure it renders the text passed via props.

**Component (`components/WelcomeMessage.js`):**

```jsx
function WelcomeMessage({ message }) {
  return <p>{message}</p>;
}

export default WelcomeMessage;
```

**Instructions:**

1. Explain the purpose of the `WelcomeMessage` component, which is to display a message passed through props.
2. Highlight the importance of testing components to ensure they render as expected.

**Test (`components/__tests__/WelcomeMessage.test.js`):**

```js
import { render, screen } from '@testing-library/react';
import WelcomeMessage from '../WelcomeMessage';

describe('WelcomeMessage Component', () => {
  it('renders the message passed as a prop', () => {
    render(<WelcomeMessage message="Hello, Next.js" />);
    const messageElement = screen.getByText('Hello, Next.js');
    expect(messageElement).toBeInTheDocument();
  });
});
```

**Instructions:**

1. Walk through writing the test, explaining each part: `render` method, `screen` object, and the `expect` assertion.
2. Run the test to show it passing, reinforcing the component behaves as expected.

### Step 2: Testing React Hooks

Next, let's test a component that uses a React hook, specifically `useState`, to toggle visibility of text.

**Component (`components/ToggleText.js`):**

```jsx
import { useState } from 'react';

function ToggleText() {
  const [isVisible, setIsVisible] = useState(false);

  return (
    <div>
      <button onClick={() => setIsVisible(!isVisible)}>Toggle</button>
      {isVisible && <p>Now you see me!</p>}
    </div>
  );
}

export default ToggleText;
```

**Instructions:**

1. Introduce the `ToggleText` component, focusing on how it uses `useState` to control the visibility of text.
2. Discuss the significance of testing user interactions, like clicks, to ensure the UI updates correctly.

**Test (`components/__tests__/ToggleText.test.js`):**

```js
import { render, screen, fireEvent } from '@testing-library/react';
import ToggleText from '../ToggleText';

describe('ToggleText Component', () => {
  it('toggles the visibility of the text on button click', () => {
    render(<ToggleText />);
    const button = screen.getByRole('button', { name: 'Toggle' });
    fireEvent.click(button);
    const visibleText = screen.getByText('Now you see me!');
    expect(visibleText).toBeInTheDocument();
  });
});
```

**Instructions:**

1. Detail the testing process, highlighting the use of `fireEvent` to simulate user clicks.
2. Emphasize the importance of dynamically testing state changes within components to ensure they react as intended.

### Conclusion

This session focused on practical examples of testing Next.js components with Jest and the React Testing Library. From rendering checks to hook functionality and handling user interactions, these examples form the basis for more complex component tests. Encourage students to explore further testing scenarios that might be relevant to their projects or interests.
