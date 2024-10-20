# Week 4 Assignment

## Fetching Data from an API

Fetching data from an API is a common task in web development. In this exercise, you will learn how to fetch data from an API and display it in your components using React hooks.

The challenge will be using hooks like `useEffect` and `useState` to fetch data from an API. You will likely not understand the entire process at first, but that's okay. The goal is to expose yourself to React hooks. 

Take notes, and bookmark the documentation you need. As you practice more, you will become more comfortable with these concepts.

## Objective

Update your Cats Cats Cats project to access an API and display the data in your components.

The API you will be using is here (you may change the breed to any breed you like):

    https://cats-cats-cats-demo.deno.dev/cats/abyssinian

Use the fetch API, useEffect, and useState to fetch the data and display it in your components.

## Instructions

In this exercise, you will be challenged to use documentation to learn how to fetch data from an API and display it in your components. You will need to use the fetch API, useEffect, and useState to accomplish this task.

You are welcome to ask questions and work together to achieve this goal.

Finally, deploy your app to [Vercel](https://vercel.com/) and link it in the about section of your README. (See the documentation at vercel.com for how to deploy your app. It is very straightforward once you push your code to GitHub. Your website will be live at `https://your-project-name.vercel.app`.)

## Stretch Goals

### Stretch Goal 1 Muli-cat

Make new page called something like `cats` or `more-cats` that requests an array instead of a single object. You can use the endpoint with a query parameter of `multi_cat=true` to get multiple cats. For example, you will get cats breeds that contain the substring "bur":

    https://cats-cats-cats-demo.deno.dev/cats/bur?multi_cat=true

### Stretch Goal 2 Error handling or loading state

Watch the video from the reading on how to handle errors and/or loading states. Implement this in your project.

### Stretch Goal 3 Custom API

Try to use a different API to fetch data. You can use any open API you like. (Avoid using API's with authentication for this exercise.)

### Stretch Goal 4 Implement StoryBook in your project

Read the StoryBook documentation and add stories to your project. This will help you to create components in isolation and document them.

Note: To use StoryBook with tailwind CSS, you add StoryBook with the command:

```bash
npx
 storybook@latest init
```

Then, you will need to add the following to your `.storybook/preview.js`:

```js
import "../src/styles/globals.css";
```

## Rubric (40 points)

- Fetch data from API: 15 points
- Display data in components: 15 points
- Deploy to Vercel: 3 points
- Stretch Goals: 7 points
  - Partial goal: 3 points
  - One goal: 5 points
  - Two goals: 7 points

## Video

NetNinja's tutorial on useEffect is a great resource to help you understand how to use useEffect in your project. (Note that he uses `.then` syntax, instead of async/await.)

[Web Dev Simplified - Learn useEffect In 13 Minutes ](https://www.youtube.com/watch?v=0ZJgIjIuY7U)

### Extra Video

If you are interested in learning more about the similarities between promise and async/await syntax, you can watch this video:

[FireShip - JavaScript Promises vs Async Await] (https://www.youtube.com/watch?v=vn3tm0quoqE)
