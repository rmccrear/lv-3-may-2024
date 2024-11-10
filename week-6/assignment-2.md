**Next.js Client Project Assignment**

In this follow-up assignment, you'll consume the server-side API you built earlier using a Next.js app. You'll learn how to use `fetch`, forms, and hooks like `useState` and `useEffect` to interact with your API and present the data to users.

### Part 1: Setting Up the Project

- **Goal**: Create a Next.js page to fetch data from your server and display it.
- **Steps**:
  1. Add a new page called `contact-me` in the `pages` folder (`pages/contact-me.js`).
  2. Set up a basic layout for the `contact-me` page and ensure the project runs locally by starting the development server.
  3. Install necessary dependencies such as `dotenv` to manage environment variables.
  4. Create a `.env.local` file to store API URLs for easy configuration.

### Part 2: Form to Interact with API

- **Goal**: Create a form to send user messages to the server.
- **Steps**:
  1. On the `contact-me` page, create a form that takes an email and a message.
  2. Use `useState` to manage the form values.
  3. When the form is submitted, use the `fetch` API to call your server's endpoint that sends an email and records the message in Upstash.
     - **Testing**: Fill out the form and check if an email is received and if the message is stored.
  4. (Bonus) Add success/error handling to display appropriate messages to users based on the API response.

### Part 3: Optional Displaying Data with useEffect (Optional)

- **Goal**: Display all messages **messages** received so far.
- **Steps**:
  1. Add an endpoint to your server that returns all stored messages. (This may be tricky depending on how you stored the data.)
  2. Create a new page called `all-messages` in the `pages` folder (`pages/all-messages.js`).
  3. Use `useEffect` to fetch all stored messages from your server when the component mounts.
  4. Display the messages in a list below the form.
     - **Testing**: Verify that all stored messages are displayed when the page loads.
  5. Add a button to manually refresh the list if new messages have been received.

**Hint**: In Redis, you can use the `scan` command to get all keys. Then, to get several keys, you can use the `mget` (multi-get) command.


```javascript

import { Redis } from "@upstash/redis";
const store = Redis.fromEnv()

// see: https://upstash.com/docs/redis/sdks/ts/commands/generic/scan
// or https://redis.io/learn/howtos/quick-start/cheat-sheet

export default async function handler(req, res) {
  // Get all keys that start with "messages:"
  const [cursor, keys] = await store.scan(0, {MATCH: "messages:*"});
  // Get all messages using the keys
  const messages = await store.mget(...keys);
  res.status(200).json(messages);
}
```

### Part 4 (optional): Enhance User Experience

- **Goal**: Provide a smooth user experience when sending and displaying messages.
- **Steps**:
  1. Use loading states to provide feedback while waiting for API responses.
  2. Clear the form after a successful submission and provide visual feedback, such as a confirmation message.
  3. Add basic CSS styling to make the form and messages visually appealing.

### Reflection
- **Goal**: Document what you learned in the process. Spend 10-15 minutes reflecting on the challenges you faced and how you overcame them.
- **Steps**:
  1. Write a summary in the README about how you used `fetch`, `useState`, and `useEffect`.
  2. Include challenges you faced and how you overcame them.
