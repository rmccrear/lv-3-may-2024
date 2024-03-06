# Day 3, Hour 1: Introduction to `useEffect` and Hooks in React

Today's session is an exciting journey into the world of React hooks, specifically focusing on `useEffect`. Before we get into the nuts and bolts of `useEffect`, let's take a step back to understand the broader picture of hooks in React and the concept of side effects.

## Recap on Class Components

As we've seen, class components were the standard in React for managing state and lifecycle events. They provide methods like `componentDidMount` for operations that need to happen after a component is rendered.

```jsx
class ExampleComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { data: null };
  }

  componentDidMount() {
    // Fetch data or perform other setup tasks
    this.setState({ data: 'Data fetched' });
  }

  render() {
    return <div>{this.state.data}</div>;
  }
}
```

This approach, while effective, could become cumbersome with complex components and lifecycle logic.

## Understanding Hooks

After reviewing class components, it's clear that while powerful, they introduce complexity, especially with lifecycle management and state. This is where hooks come in.

### What Are Hooks?

Hooks are functions that let you “hook into” React state and lifecycle features from function components. They simplify component logic, making it easier to separate concerns and reuse stateful logic across components.

### The Revolution of Hooks

Hooks represent a shift in how you can use React features, making code more readable and maintainable. They allow functional components to manage state and side effects, tasks that were once only possible in class components.

## Demystifying Side Effects

In React, side effects are operations that affect other components, or interact with the outside world (like fetching data, directly manipulating the DOM, or setting up subscriptions). These operations don’t fit into the React dataflow (props down, events up).

### Why `useEffect`?

`useEffect` is a hook designed to manage side effects in functional components. It tells React that your component needs to do something after render. React will remember the function you passed (the “effect”) and call it later after updating the DOM.

## Simplified Data Fetching with `useEffect`

Now, armed with an understanding of hooks and side effects, let's revisit our example of fetching Pokémon data with `useEffect`. This time, consider how `useEffect` enables us to manage side effects efficiently:

```jsx
import React, { useState, useEffect } from 'react';

function SimplePokemonList() {
  const [pokemonOne, setPokemonOne] = useState({});
  const [pokemonTwo, setPokemonTwo] = useState({});

  useEffect(() => {
    async function fetchData() {
      const responseOne = await fetch('https://pokeapi.co/api/v2/pokemon/1');
      const dataOne = await responseOne.json();
      setPokemonOne(dataOne);

      const responseTwo = await fetch('https://pokeapi.co/api/v2/pokemon/2');
      const dataTwo = await responseTwo.json();
      setPokemonTwo(dataTwo);
    }

    fetchData();
  }, []);

  return (
    <div>
      <div>{pokemonOne.name}</div>
      <div>{pokemonTwo.name}</div>
    </div>
  );
}
```

In this example, `useEffect` replaces the need for `componentDidMount`, allowing us to fetch data right after the component mounts. The empty dependency array `[]` tells React this effect doesn’t depend on any values from props or state, so it only runs once after the initial render.

## Conclusion

With a deeper understanding of hooks and the concept of side effects, you can appreciate how `useEffect` simplifies handling side effects in functional components. This marks a significant evolution from the class component paradigm, enabling more intuitive and maintainable component development.

<!--! Hour 2 -->

# Day 3, Hour 2: Handling API Responses

Building on our understanding of `useEffect` from the previous hour, we now turn our attention to managing API responses more effectively. Specifically, we'll focus on handling loading states, displaying fetched data, and introducing error handling in our API calls.

## Managing Loading States

A critical aspect of a good user experience in applications that fetch data is providing feedback about what's happening. A loading state informs the user that data is currently being retrieved.

### Implementing Loading States

Let's adjust our `SimplePokemonList` component to include a loading state:

```jsx
import React, { useState, useEffect } from 'react';

function SimplePokemonList() {
  const [pokemonOne, setPokemonOne] = useState({});
  const [isLoading, setIsLoading] = useState(false);
  const [error, setError] = useState('');

  useEffect(() => {
    setIsLoading(true);
    async function fetchData() {
      try {
        const response = await fetch('https://pokeapi.co/api/v2/pokemon/1');
        if (!response.ok) {
          throw new Error('Failed to fetch');
        }
        const data = await response.json();
        setPokemonOne(data);
      } catch (error) {
        setError(error.message);
      } finally {
        setIsLoading(false);
      }
    }

    fetchData();
  }, []);

  if (isLoading) return <div>Loading...</div>;
  if (error) return <div>Error: {error}</div>;

  return (
    <div>
      <h1>{pokemonOne.name}</h1>
    </div>
  );
}
```

In this enhanced version, we've introduced a loading state and error handling. The `isLoading` flag is used to display a loading message while the data is being fetched. After the fetch operation is complete or if an error occurs, we update the state accordingly to reflect the change in the UI.

## Introduction to Error Handling

Error handling in API calls is crucial for building resilient applications. Users should be informed if data cannot be retrieved, rather than leaving them waiting or showing an incomplete interface.

### Error Handling in Practice

The try-catch block in our `fetchData` function allows us to catch any errors that occur during the fetch operation. By setting an `error` state, we can display an appropriate message to the user.

## Key Takeaways

- **Loading States**: It's essential to manage loading states in your application to keep users informed about ongoing data fetching operations. This can be as simple as displaying a "Loading..." message.
- **Error Handling**: Proper error handling ensures that your application can gracefully deal with failed API calls. Displaying clear error messages improves the user experience and aids in debugging.

- **Simplifying Fetch Operations**: Using `async/await` along with try-catch blocks simplifies the syntax for making API calls and handling responses, making your code cleaner and easier to understand.

## Conclusion

Incorporating loading states and error handling in your React applications significantly improves user experience and application reliability. By building on the foundations of `useEffect`, we've seen how to effectively manage API responses, laying the groundwork for more complex and interactive web applications.
