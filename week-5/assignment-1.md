### Cats, Cats, Cats Part 3

## Proxy Server and New Endpoints

In this assignment, you will continue working on the **Cats, Cats, Cats** project from Part 2, which was completed last week. You will create a new branch, set up a proxy server, and add new API endpoints to your project.

### Step-by-Step Instructions

1. **Create a Branch**

   - Create a new branch named `week-5` or `next-api` (whichever you prefer).

   **Test**: Verify that your new branch is created by running `git branch` and ensuring your branch name is listed and checked out.

2. **Write a Proxy Server for Cats Data**

   - In the `/api/cats` folder, write a proxy server that fetches cat data directly from the api-ninjas server. You will need an API key for this task.

   **Test**: Use Postman to send a request to `/api/cats` and save the request in a Postman collection. Also, visit the endpoint in your browser to verify the response. Ensure you receive the expected cat data from the api-ninjas server.

3. **Update Pages to Use Your Endpoint**

   - Update your pages to fetch data from your own endpoint at `/api/cats` instead of directly from the external API.

   **Test**: Visit the updated pages in your browser and check if the cat data is displayed correctly. Confirm that the data is coming from your proxy server by checking the network requests in your browser's developer tools. Save the updated request in your Postman collection.

4. **Create Additional Endpoints**

   - In your `/api` folder, create two new endpoints:
     - `/api/pokemon` to fetch data from the [Pokémon API](https://pokeapi.co/)
     - `/api/trivia` to fetch trivia questions from the [Open Trivia Database](https://opentdb.com/api_config.php)

   **Test**: Use Postman to send requests to `/api/pokemon` and `/api/trivia`. Save these requests in your Postman collection. Also, use your browser to verify the responses and ensure you receive the expected data from both endpoints.

5. **Bonus Task**

   - Try to use another API that requires an API key, such as [Weatherbit.io](https://www.weatherbit.io/).

   **Test**: Use Postman to send a request to the new endpoint and save it in your Postman collection. Verify the response in Postman and ensure the data is returned correctly. If the API requires an API key, ensure it is handled properly and securely.

6. **Bonus Task: Clean Up Data**

   - Clean up your data before returning it to your user. The original data may include extraneous or obscure data that is not needed by your app. Create a new object in your API route function that only contains the information that is salient to your user.

   **Test**: Verify in Postman that the returned data only includes the cleaned-up fields. Save this request in your Postman collection.

7. **Test Your Code**

   - After each step, make sure your code works correctly before moving on to the next step. Save all requests in your Postman collection for easy access and testing.

### Objective

The objective of this assignment is to further develop your **Cats, Cats, Cats** project by integrating new data sources through a proxy server and additional endpoints. This will enhance your skills in using APIs and working with server-side logic.

### Stretch Goals

- **Multi-Cat Page**: Create a new page called `more-cats` that fetches multiple cat entries from your `/api/cats` endpoint.
- **Error Handling**: Add error handling and loading states for your API requests.
- **Storybook**: Integrate Storybook to document your components.

### Rubric (30 points)

- **Proxy Server Setup** (10 points): Proxy server fetches cat data correctly.
- **Page Update** (5 points): Pages updated to use the new endpoint at `/api/cats`.
- **New Endpoints** (10 points): Two additional endpoints for Pokémon and trivia data are created and function properly.
- **Bonus** (5 points): Successfully integrate another API requiring an API key.

### Resources

- [Pokémon API Documentation](https://pokeapi.co/)
- [Open Trivia Database](https://opentdb.com/api_config.php)
- [Weatherbit.io API](https://www.weatherbit.io/)

### README Requirement

Create a `README.md` file in your project root directory. Remember the audience of your README is a person stumbling on your project for the first time. The README should include:

- **Project Overview**: A brief description of what the project does.
- **Setup Instructions**: How to run the project locally, including dependencies and installation steps.
- **Endpoints**: Document the `/api/cats`, `/api/pokemon`, and `/api/trivia` endpoints. (Very briefly describe the data that is returned from each of these endpoints.)
- **Postman Collection**: Include screenshots of the Postman requests for the three APIs (`/api/cats`, `/api/pokemon`, `/api/trivia`). Ensure that each request is clearly labeled.
- **Deployed Link**: Add the link to your deployed project (e.g., `https://your-project-name.vercel.app`).

