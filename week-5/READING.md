**Creating API Routes in Next.js**

**Summary:**
This reading exercise covers the concept of creating API routes in Next.js, a framework built on React. You will learn how to set up and handle API routes, which allow you to create backend endpoints without the need for a dedicated server.

**Article 1: Creating API Routes - Next.js**
[Read the article here](https://nextjs.org/learn-pages-router/basics/api-routes/creating-api-routes).

This article introduces the basics of creating API routes in Next.js. It explains how API routes allow you to add backend functionality directly in your Next.js applications, eliminating the need for a separate server. You will learn about file structure, the creation of simple routes, and how to return JSON responses.

   1. Where are API route files stored? (Which file or directory?)
   2. What do the arguments `req` and `res` represent in the function that defines an API route?
   3. Can you find this example file in your Next.js project? If so, try and modify it to return a different JSON object. 

**Article 2: Creating API Routes - refine.dev**
[Read the article here](https://refine.dev/blog/next-js-api-routes/#how-to-create-api-routes-in-nextjs).

This blog post from refine.dev provides an in-depth look into creating API routes in Next.js, covering more advanced concepts such as using environment variables to keep sensitive data secure. The article also discusses practical use cases of API routes, such as handling form submissions and fetching external data.

   1. What is one benefit of using API routes?
   2. Where do we store secrets and sensitive data?
   3. How can we repsond to different HTTP methods in an API route, like `POST`?
   4. What is the purpose of naming a file with square brackets, like `[id].js` or `[number].js`?

**Connection to this week's assignment:**

   This week we will create a new API route in Next.js. Your API should respond to a `GET` request by returning a JSON object. You will be required to use a `.env.local` file to store your environment variables securely. Finally, you will use the API route to fetch data in your application.
 