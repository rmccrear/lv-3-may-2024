**Magic Link Authentication Assignment**

In this assignment, you will build upon the server project to implement a simple "magic link" authentication system. This will involve creating unique login links sent to a user's email, handling secure logins, and managing user sessions.

### Part 1: Magic Link Setup

- **Goal**: Set up your server to send a "magic link" that users can click to log in.
- **Steps**:
  1. Create an endpoint in your `/api` folder called `send-magic-link.js`.
  2. The endpoint should accept a POST request with a user email as input. If the email is valid, it should generate a unique token (a random  number will do), store it using Upstash, and send an email containing the login link (e.g., `https://your-app.com/login?token=uniqueToken`).
     - **Testing**: Test the endpoint by sending a POST request with an email. Check your inbox for the login link and ensure it contains a unique token.
  3. Integrate Resend to send the email with the magic link, as in the previous assignment.
  4. Reflect on the process in the README:
     - Update the README to explain how the magic link is generated and the purpose of the token.



- **Testing**: Test the magic link by following these steps:
  1. Generate a magic link by sending a POST request to `send-magic-link.js` with your email.
  2. Check that the token is correctly stored in Upstash under `magic_token:<userEmail>`.
  3. Click the link or manually send a `GET` request to `validate-token.js` with the token.
  4. Verify that the endpoint correctly checks the token validity, creates a session token, and returns a success response.
  5. Attempt using an expired or invalid token to ensure the correct error response is returned.
- **Steps**:
  1. Create an endpoint in your `/api` folder called `validate-token.js`.
  2. The endpoint should accept a `GET` request with a `token` parameter. Use Upstash to check if the token is valid.
     - If the token is invalid or expired, return an error response.
     - **Testing**: Test the endpoint by visiting the login link received via email. Verify that the response correctly indicates whether the login was successful or not.
  3. Store the session token in the client-side state or `localStorage` to maintain the user's login session. You will need this for later when your user tries to interact with password protected parts of the site.
  4. Reflect on the process in the README:
     - Update the README with a diagram showing the flow of authentication from sending the magic link to logging in.

## Create protected routes.

- Some routes should only be accessed by a valid user. You will check to see if the user if valid by if they have the token you sent with magic link.

1. Create endpoints to store and retrieve user-specific data:
   - `add-favorite.js`: Accepts a POST request with a `userEmail` ,  `favorite`, and `token`. Store the "favorite" in Upstash under the user's key (e.g., `favorite:userEmail`).
   - In `add-favorite.js` check that the token matches the token you have stored in `magic_token`. If it does, proceed. If not, return with a 401 Unauthorized error. 
     - **Testing**: Use Postman to test to see if add-favorites work. Double check in the Upstash dashboard to see if it stored the data.
   - &#x20;`get-favorite.js`: Accepts a `GET` request with a `userEmail` and retrieves the favorite cat associated with that user. This does not have to be password protected be cause we are sharing favorites with the world.
   - **Testing**: Test the endpoint by sending appropriate requests and verifying that the data is stored and retrieved correctly.
   - (Optional: set other sorts of user data. You may explore the use of arrays or objects in Redis.)
2. Reflect on the process in the README:
   - Add a section in the README to explain how user data is stored and retrieved, with examples.

### Redis Cheat Sheet

Here are some helpful conventions for naming Redis variables:

- **Session Tokens**:

  - Use `session:<userEmail>` to store session tokens for each user.
  - Example: `session:user@example.com`.

- **Magic Link Tokens**:

  - Use `magic_token:<userEmail>` to store the magic link tokens.
  - Example: `magic_token:user@example.com`.

- **User Data**:

  - Favorite Cat: `favorite:<userEmail>` to store the favorite cat for a specific user.
  - Messages: `messages:<userEmail>` to store all messages for a specific user as an array.
  - Favorites: `favorites:<userEmail>` to store all favorites for a specific user as an array.
  - Example: `favorite:user@example.com`, `messages:user@example.com`, `favorites:user@example.com`.

- 

  - Keys can be created dynamically by concatenating strings, allowing flexibility based on user input or resource type (e.g., `favorite:${userEmail}` to create keys for different users dynamically).

  - Use a consistent naming pattern that includes the resource type and identifier (e.g., user email).

  - Separate different parts of the key with a colon (`:`) for better readability and organization. 

