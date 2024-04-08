# Day 2, Hour 1: Introduction to React State with `useState`

Today, we embark on understanding one of React's most powerful features for dynamic application development: state management. We will explore the `useState` hook, which allows us to add state to our function components in a clean and efficient way.

## Understanding State in JS

Here is a simple demo that shows state for a counter in commonJS and html, feel free to include a greeting function and have it change the greeting based on the user passed in

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Counter Example</title>
  </head>
  <body>
    <h1>Count: <span id="count">0</span></h1>
    <button id="incrementBtn">Increment</button> 

    <script>
      // Define the state
      let count = 0;

      // Function to increment the count
      function incrementCount() {
        count += 1; // Increment the count
        document.getElementById('count').textContent = count; // Update the UI
      }

      // Add click event listener to the button
      document
        .getElementById('incrementBtn')
        .addEventListener('click', incrementCount);
    </script>
  </body>
</html>
```

## Understanding State in React

Think of state in a React application as the current situation of a component. Just like in real life, where your mood can change from happy to sad, a component's state can change in response to interactions. The `useState` hook gives us a way to track these changes.

## Using the `useState` Hook

To utilize state within our components, we start by importing `useState` from React. This hook lets us create state variables in functional components, managing their updates and reflecting those changes in the UI.

### Implementing a Counter Component

Let's create a simple counter that increases, decreases, and resets based on user interaction. This example will help solidify your understanding of state management with `useState`.

1. **Start by Creating a New Component**: In your `src/app/` directory, create a file for our counter component. Let's name it `Counter.js`.

2. **Implement the Counter Logic**: Inside `Counter.js`, we'll start with the 'use client'; directive to ensure this runs client-side, then set up our component with `useState` to manage the counter's value.

   ```jsx
   // At the top of your file to ensure client-side execution
   'use client';

   import React, { useState } from 'react';

   function Counter() {
     // Initialize the counter state
     const [count, setCount] = useState(0);

     // Function to increment the counter
     const increment = () => setCount(count + 1);

     // Function to decrement the counter
     const decrement = () => setCount(count - 1);

     // Function to reset the counter
     const reset = () => setCount(0);

     // The UI of our component
     return (
       <div>
         <h2>Counter: {count}</h2>
         <button onClick={increment}>+</button>
         <button onClick={decrement}>-</button>
         <button onClick={reset}>Reset</button>
       </div>
     );
   }

   export default Counter;
   ```

3. **Understanding State Updates**: In our component, we use `setCount` to update our `count` state. Notice how we pass a new value to `setCount` to update our state. React then re-renders the component to reflect the new state in the UI.

### Best Practices for Updating State

- **Avoid Direct Mutations**: Always use the setter function returned by `useState` (e.g., `setCount`) for updates to ensure React is aware of the state change and can update the component accordingly.
- **Functional Updates**: If the new state depends on the old state, you should use a functional update, like `setCount(prevCount => prevCount + 1)`, to ensure reliability.

## Wrapping Up

By implementing a simple counter, we've taken our first steps into state management in React. This concept is fundamental to building interactive and dynamic web applications. Keep experimenting with `useState` to build

<!--! Hour 2  -->

# Day 2, Hour 2: Managing Form Input State with `useState`

In this session, we delve into handling forms in React, leveraging the `useState` hook for input state management, and understanding the distinction between controlled and uncontrolled components.

## Controlled vs Uncontrolled Components

In React, form inputs can be managed in two ways: through controlled and uncontrolled components.

- **Controlled Components**: Here, the form data is handled by the React component state. This means every state mutation will have an associated handler function, making React the "single source of truth."
- **Uncontrolled Components**: These manage their own state internally and update it based on user input without React's direct involvement. They can be likened to traditional HTML form inputs.

### Creating a Controlled Component Form

Let's build a simple form that captures user input and displays it upon submission, showcasing how to use `useState` for managing form input states in a controlled manner.

1. **Setting Up the Form Component**: In your `src/app/` directory, create a new file for our form component. Let's call it `UserForm.js`. Remember to include 'use client'; at the top for client-side execution.

2. **Implementing the Form with Controlled Inputs**:

   ```jsx
   'use client';

   import React, { useState } from 'react';

   function UserForm() {
     // State to store the input value
     const [inputValue, setInputValue] = useState('');

     // Handler to update state based on input changes
     const handleInputChange = (e) => {
       setInputValue(e.target.value);
     };

     // Handler for form submission
     const handleSubmit = (e) => {
       e.preventDefault(); // Preventing the default form submission behavior
       alert(`Form submitted with input: ${inputValue}`);
       setInputValue(''); // Reset input value after submission
     };

     return (
       <form onSubmit={handleSubmit}>
         <label>
           Your Name:
           <input type="text" value={inputValue} onChange={handleInputChange} />
         </label>
         <button type="submit">Submit</button>
       </form>
     );
   }

   export default UserForm;
   ```

3. **Understanding the Code**:

   - The input field is a **controlled component** because its value is tied to the React state (`inputValue`), and it updates on every keystroke through `handleInputChange`.

   - When the form is submitted, `handleSubmit` is triggered, displaying the input value in an alert and then clearing the form.

### Best Practices

- **Always Use Controlled Components for Forms**: This approach gives you full control over the form's data and behavior, making it easier to validate or manipulate form data on the fly.

- **Centralize Form State**: For forms with multiple inputs, consider using a single state object to manage all input values. This makes handling complex forms more streamlined.

## Wrapping Up

By creating a controlled component form, we've explored how to efficiently manage form input states in React. Understanding the distinction between controlled and uncontrolled components is vital for effective form handling and ensuring data consistency across your application.
