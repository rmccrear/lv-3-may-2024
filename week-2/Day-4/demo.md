# Day 4, Hour 1: Client-Side Navigation and Data Mapping

In today's session, we'll explore the power of client-side navigation in Next.js using the `Link` component, followed by an introduction to rendering lists in React. These concepts are fundamental to creating interactive and efficient web applications.

## Client-Side Navigation with `Link`

Next.js enhances React's capabilities with features like client-side navigation, enabling faster, smoother transitions between pages without a full page reload.

### Using the `Link` Component

The `Link` component provided by Next.js is used to enable client-side navigation between pages. It's similar to using `<a>` tags in HTML but optimized for Next.js applications.

```jsx
import Link from 'next/link';

function NavigationMenu() {
  return (
    <nav>
      <ul>
        <li>
          <Link href="/home">Home</Link>
        </li>
        <li>
          <Link href="/about">About</Link>
        </li>
      </ul>
    </nav>
  );
}
```

This code snippet creates a simple navigation menu. Clicking on these links will navigate the user to the respective pages without reloading the entire page, thanks to Next.js's client-side navigation.

## Rendering Lists with `map` and the `key` Prop

Rendering lists in React is often accomplished using the JavaScript `map()` method. It's a powerful way to transform arrays into JSX elements. However, when rendering lists, it's crucial to provide a unique `key` prop to each element for performance and stability reasons.

### Implementing a List Render

Let's render a list of fetched items. For simplicity, we'll assume we have an array of items fetched from an API.

```jsx
function ItemList({ items }) {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}
```

This example demonstrates how to use `map` to iterate over an array of items and render each one as a list item (`<li>`) in JSX. The `key` prop is given a unique identifier (in this case, `item.id`) to help React identify which items have changed, been added, or removed. This improves performance and prevents potential issues with item reordering.

## Code Example: Navigation and Displaying a List

Combining our learning, let's implement a component that includes client-side navigation and displays a list of items:

```jsx
import Link from 'next/link';
import React, { useEffect, useState } from 'react';

function App() {
  const [items, setItems] = useState([]);

  useEffect(() => {
    // Fetch items from an API and set them
    setItems([
      { id: 1, name: 'Item 1' },
      { id: 2, name: 'Item 2' },
    ]);
  }, []);

  return (
    <div>
      <NavigationMenu />
      <ItemList items={items} />
    </div>
  );
}

// Assume NavigationMenu and ItemList are defined as above
```

This component showcases how to structure a Next.js app with client-side navigation and dynamic list rendering. We start with fetching data (mocked for simplicity) and storing it in state. Then, we render a navigation menu and a list of items using the `Link` component for navigation and `map` for list rendering, respectively.

## Conclusion

Today, we've covered essential techniques in Next.js and React for creating interactive web applications. Client-side navigation with the `Link` component enhances user experience by enabling fast, seamless transitions between pages. Meanwhile, understanding how to render lists with `map` and the importance of the `key` prop is crucial for efficiently displaying dynamic data.

<!--! Hour 2  -->

# Day 4, Hour 2: Conditional Rendering and Passing Props

In this hour, we will delve into two powerful concepts in React: conditional rendering and passing data to components using props. These techniques allow for more dynamic and responsive user interfaces. To put these concepts into practice, we'll create a component that toggles its layout between a list and a grid view based on user interaction.

## Conditional Rendering

Conditional rendering in React enables you to display different components or results based on certain conditions. It's like making a decision in real life: if one thing is true, you choose option A; otherwise, you choose option B.

### Implementing Conditional Rendering

You can use JavaScript operators like the ternary operator to implement conditional rendering in your components. Here's a simple example:

```jsx
function WelcomeMessage({ isLoggedIn }) {
  return (
    <div>{isLoggedIn ? <h1>Welcome back!</h1> : <h1>Welcome, guest!</h1>}</div>
  );
}
```

This component displays a different message depending on whether the user is logged in.

## Passing Data to Components Using Props

Props (short for properties) are a way of passing data from parent to child components, enabling you to make your components more dynamic and reusable.

### Example: Passing Props

Let's pass a list of items to a component that renders them:

```jsx
function ItemList({ items }) {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}
```

Here, `ItemList` receives `items` as props and renders a list of items accordingly.

## Code Example: Toggling Layouts

Now, let's create a component that can switch between displaying items in a list view and a grid view based on user interaction. This example will demonstrate both conditional rendering and the use of props.

```jsx
import React, { useState } from 'react';

function ToggleLayout({ items }) {
  const [isGridView, setIsGridView] = useState(false);

  return (
    <div>
      <button onClick={() => setIsGridView(!isGridView)}>
        Switch to {isGridView ? 'List' : 'Grid'} View
      </button>
      <div style={{ display: isGridView ? 'grid' : 'block' }}>
        {items.map((item) => (
          <div
            key={item.id}
            style={{ margin: '10px', border: '1px solid black' }}
          >
            {item.name}
          </div>
        ))}
      </div>
    </div>
  );
}
```

In this component, `isGridView` state determines the current layout. The button toggles this state between true and false, and the container's `display` style switches between 'grid' and 'block' accordingly. Each item's name is displayed in a div, which aligns according to the current layout style.

## Conclusion

Today, we explored conditional rendering and passing data with props, foundational concepts for building dynamic React applications. Our example component illustrates how these concepts can be applied to create interactive and adaptable UIs. By
