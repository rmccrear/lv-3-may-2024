# Server Project Assignment

In this assignment, you'll build a server that can send emails and store user data from users such as "likes," "messages," and "favorites". You'll progress through setting up email notifications, creating data persistence, and implementing login functionality using a "magic link".

### Part 1: Email Integration

- **Goal**: Set up your server to send an email when an API endpoint is hit, using Resend.
- **Steps**:
  0. Create a NEW Next.js project with your terminal and sync it to github. You may call it "capstone" if you wish to use this repo to get started on you capstone project.
  1. Create an endpoint in your `/api` folder called `send-email.js`.
  2. The endpoint should return a JSON object with a message that says "Email sent!" or "Error sending email!" based on a variable called `success`.
     - **Testing**: Test this endpoint by sending a request (e.g., using Postman or CURL) and verify that the correct JSON message is returned based on the success or failure of the email sending process.
  3. Create an account on [resend.com](https://resend.com).
  4. Integrate Resend into your app by adding the API key to your environment variables.
  5. Send an email to yourself using the API endpoint you just created.
     - **Testing**: Check your email inbox to confirm that the email has been received. Additionally, you can look in the dashboard at resend.com to verify if the email was sent successfully.
       If not, check the server logs for any error messages.
  6. *(Optional)* Set up your own domain to send email to others.
  7. **Reflect on the process by adding to your README**:
     - A diagram of the server architecture.
     - A README update that explains the server architecture and includes the diagram.

### Part 2: Key-Value Store on the Server

- **Goal**: Use Upstash to add data persistence to your server.
- **Steps**:
  1. On the Vercel dashboard, click "Storage" to add an Upstash KV database.
  2. Add the Upstash API keys to your environment variables.
  3. Create an endpoint in your `/api` folder that increments a counter each time it is hit.
     - **Testing**: Use Postman or CURL to hit the endpoint multiple times, then use another endpoint or console log to retrieve the counter value and verify that it increments correctly.
  4. Create another endpoint that accepts a query parameter called `message` and stores it in Upstash.
     - **Testing**: Send a request with different `message` values and verify that they are correctly stored in Upstash by retrieving them using another endpoint or logging them to the console.
  5. Reflect on the process by adding to your README:
     - A diagram of the server architecture.
     - A README update that explains the server architecture and includes the diagram.
 
### Part 3: Combine Features

* **Goal**: Create a fully functioning endpoint that sends email and records data.
* **Steps**:
  1. Create an endpoint that accepts both `message` and `email` parameters.
  2. The handler should send an email to you that includes the message and the sender's email in the body of the email so you can get back to them.
     - **Testing**: Send a request with sample `message` and `email` values and verify that you receive the email with the correct content.
  3. Additionally, store the message in Upstash to maintain a record of sent emails.
     - **Testing**: Retrieve the stored messages from Upstash to verify that each message is correctly recorded. Additionally, check the Upstash dashboard to confirm the data is being stored.
  4. Reflect on the process by update the README to explain the  server architecture, including a diagram.

### Redis Client Reference

Upstash is a service that lets you use a simple database called Redis in your app. Redis has its own commands you use to interact with it. (This is called the Redis API.)

Here is a cheat sheet.

- **Setup Upstash KV store**:

  ```javascript
  import { createClient } from '@vercel/kv';

  export default async function handler(req, res) {
    const store = createClient({
      url: process.env.KV_REST_API_URL,
      token: process.env.KV_REST_API_TOKEN
    });
    // Your logic here...
  }
  ```

- **Increment a value**:

  ```javascript
  await store.increment('count');
  ```

- **Set a value**:

  ```javascript
  await store.set('fruit', 'apple');
  ```

- **Get a value**:

  ```javascript
  const fruit = await store.get('fruit');
  ```

In Redis, keys can be any string. Values can be any string, number, or JSON object. You could have a key called `likes` and a value of `5`. You could have a key called `mrnobody@gmail.com` and a value of `Hello! I like your site!`.

Example:

```javascript
await store.set('mrnobody@gmail.com', 'Hello! I like your site!');
```

