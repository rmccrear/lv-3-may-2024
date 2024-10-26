### Cats, Cats, Cats Part 4

## Consuming Endpoints and Creating Pages

In this assignment, you will build on your **Cats, Cats, Cats** project by consuming the endpoints you created in Part 3. You will create new pages in your `/src/pages` directory to display data fetched from the endpoints.

### Step-by-Step Instructions

**Styling Requirement**: Use [Tailwind CSS](https://tailwindcss.com/) for styling each of the pages you create. Ensure that your pages are visually appealing and consistent.

1. **Create Folders for New Pages**

   - In the `/src/pages` directory, create new folders for each page you need:
     - `pokemon/index.js` for the Pokémon data.
     - `trivia/index.js` for the trivia questions.
     - `more-cats/index.js` for multiple cat entries (if you completed the multi-cat stretch goal).

2. **Fetch Data in Each Page**

   - In each new page, use `fetch` along with React hooks (`useEffect` and `useState`) to request data from the corresponding API endpoint you created in Part 3.
   - Ensure that each page is functional and displays the data clearly.

   **Example for** `/src/pages/pokemon/index.js`:

   ```javascript
   import { useEffect, useState } from 'react';

   export default function Pokemon() {
     const [pokemonData, setPokemonData] = useState(null);

     async function fetchPokemon() {
       try {
         const response = await fetch(`/api/pokemon/pikachu`);
         const data = await response.json();
         setPokemonData(data);
       } catch (error) {
         console.error('Error fetching Pokémon data:', error);
       }
     };

     useEffect(() => {
       fetchPokemon();
     }, []);

     if (!pokemonData) {
       return <div>Loading...</div>;
     }

     return (
       <div>
         <h1>Pokémon Data</h1>
         <p>Name: {pokemonData.name}</p>
       </div>
     );
   }
   ```

3. **Create the Trivia Page**

   - Create `trivia/index.js` to fetch and display trivia questions from your `/api/trivia` endpoint.
   - Include appropriate error handling and loading states.

4. **Create the More Cats Page**

   - If you completed the multi-cat stretch goal in Part 3, create `more-cats/index.js` to display multiple cat entries from the `/api/cats` endpoint.

5. **Test Your Pages**

   - Visit each page in your browser (`/pokemon`, `/trivia`, `/more-cats`) to verify that the data is being displayed correctly.
   - Use the browser developer tools to check network requests and ensure that the data is being fetched from your custom API endpoints.

### Objective

The objective of this assignment is to consume the custom API endpoints you created in Part 3 and display the data on corresponding pages in your application. This will help you practice working with API data and building dynamic pages in a React application.

### Stretch Goals

- **Tailwind Styling**: Apply Tailwind CSS styling to all pages to enhance the visual appeal and user experience. Ensure consistent use of styles and responsiveness.

- **Custom Components**: Create and use custom components within the pages. Extract repeated elements such as displaying data or error messages into separate components and use them across different pages.

- **Component Reusability**: Extract repeated elements, such as loading states or error messages, into reusable components.

### Rubric (30 points)

- **Fetch Data and Display** (15 points): Successfully fetch data from each API endpoint and display it on the page.
- **Error Handling and Loading States** (5 points): Properly handle errors and loading states for each page.
- **Page Structure and Organization** (5 points): Organize your files and components in a clear and logical manner.
- **Bonus** (5 points): Successfully implement at least one stretch goal, including creating and using custom components.

### Resources

- [React useEffect Hook](https://reactjs.org/docs/hooks-effect.html)
- [MDN Fetch API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
- [React Component Organization](https://reactjs.org/docs/faq-structure.html)

