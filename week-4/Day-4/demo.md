# Week 4, Day 4, Hour 1: Basic Unit Testing in Next.js with Jest

Welcome to the introduction of unit testing within a Next.js project, focusing on client-side code. Today, we'll delve into setting up Jest for Next.js and crafting simple tests to ensure components render correctly and display the intended content. We will follow the manual configuration instructions as described in the official Next.js documentation under `docs/testing/jest`.

## Setting Up Jest for Next.js

First, we’ll start a new Next.js application as we have done in previous assignments. Then, we’ll proceed with setting up Jest by following the manual setup instructions provided in the official Next.js documentation.

### Installation

Ensure Jest and necessary testing libraries are added to your project:

```sh
npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom
```

### Configure Jest

After installation, generate a `jest.config.js` file at the root of your project by running:

```sh
npm init jest@latest
```

Select "JavaScript" for the configuration file type and accept the default options. Once generated, replace the contents of `jest.config.js` with the following:

```js
const nextJest = require('next/jest');

const createJestConfig = nextJest({
  dir: './',
});

const customJestConfig = {
  testEnvironment: 'jest-environment-jsdom',
};

module.exports = createJestConfig(customJestConfig);
```

**Note:** We will skip sections in the documentation regarding:

- Optionally adding a snapshot test
- Optional custom matchers extension
- Handling Absolute Imports and Module Path Aliases

## Writing Basic Tests

### Example: Testing Text Content

```js
import Link from 'next/link';

export default function Home() {
  return (
    <div>
      <h1>Home</h1>
      <Link href="/about">About</Link>
    </div>
  );
}
```

In the nest file

```js
import '@testing-library/jest-dom';
import { render, screen } from '@testing-library/react';
import Page from '@/app/page';

describe('Page', () => {
  it('renders a heading', () => {
    render(<Page />);

    const heading = screen.getByRole('heading', { level: 1 });

    expect(heading).toBeInTheDocument();
  });
});
```

Explore these docs:
https://testing-library.com/docs/queries/about

## Conclusion

Today's session focused on the basic setup and initial testing strategies within a Next.js project using Jest. These foundational skills will enhance the reliability and quality of your web applications by ensuring that components function as intended.

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
