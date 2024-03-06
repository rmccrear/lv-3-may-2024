# Introduction to Next.js and React Basics

Welcome to your journey into the world of Next.js and React. As we dive into these topics, we'll be taking it one step at a time, ensuring you grasp the foundational concepts with clarity and confidence. Let's start by exploring what makes Next.js and React so special in the landscape of web development.

## Understanding Frameworks and Libraries

Imagine you're building a model airplane. A **framework** like Next.js is like getting a model kit that comes with all the parts and an instruction manual. It guides you on how to put it together, providing structure and rules you should follow for the best outcome. On the other hand, a **library** like React is like the individual parts themselves, which you can use in any way you like to build your model airplane or something else entirely.

### React: The Building Blocks

React is a JavaScript library for creating user interfaces. Think of React components as lego pieces. Each piece (or component) can be used and reused to build the structure of your application, just like how you would build different structures by snapping lego pieces together. This makes React extremely versatile and powerful for developing complex applications.

### JSX: A Blend of Magic

JSX stands for JavaScript XML. It allows you to write your components in a way that looks similar to HTML, which can be more intuitive when designing UIs. If HTML is the language of the web, think of JSX as a dialect that speaks both JavaScript and HTML. It's like being bilingual, offering you the best of both worlds.

### Next.js: Building with a Blueprint

Moving to Next.js, it's a framework built on top of React. It provides a set of predefined ways to structure your application, similar to the 7-1 SASS structure you're familiar with, where everything has its place, and you're working within a guided system. This system helps manage complexity, especially as projects grow. It's like having a blueprint for constructing a building, ensuring that everything fits together correctly.

## Diving Deeper: Components and Pages

In React and Next.js, everything revolves around components. These are self-contained pieces of your application. Just like in Object-Oriented Programming (OOP), where you encapsulate properties and methods, components encapsulate their layout and functionality. This encapsulation makes it easier to manage and reuse code throughout your application.

### Creating Our First Component

Let's create a simple greeting component together:

```js
const Greeting = () => {
  return <h1>Hello, World!</h1>;
};
```

This component is a function that returns JSX, rendering an `<h1>` tag with a greeting. Simple, right?

### Exploring Next.js Project Structure

When we create a Next.js project, it organizes files in a way that might remind you of the 7-1 SASS structure, with specific directories for pages, components, and static files. This organization helps keep your project clean and navigable, especially as it scales.

### Tour of the Documentation

Now, let's take a moment to explore the [Next.js Documentation](https://nextjs.org/docs) and the [React Documentation](https://reactjs.org/docs). Opening the docs, notice how they're structured, offering guides, API references, and more. Familiarize yourself with navigating these resources, as they will be invaluable on your development journey.

### From Bootstrap to Next.js

You've used Bootstrap before, a library that offers ready-made components to speed up development. While React and Next.js also speed up development, they do so by providing a robust system for building custom components and applications, rather than offering pre-styled components. However, the underlying principle of reusability and efficiency remains a common thread.

<!--! Hour 2  -->

# Hour 2: Exploring the Next.js File Structure

In this session, we'll navigate through the file structure of a Next.js project, emphasizing the organization within the `src/` directory, the significance of the `public/` directory for static assets, and how to manage your project's configuration and assets for a clean, efficient development workflow.

## Navigating the `src/` Directory

Within the `src/` directory of your Next.js project, you'll find several key components that form the backbone of your application's structure and functionality:

- **`app/` Directory**: This is where the core of your application lives. It includes your project's entry points and the global layout that wraps around your application.

  - **`page.js`**: Acts as the entry point for a route in your application. You can think of it like the front door to a specific part of your house, guiding visitors to where they want to go.

  - **`layout.js`**: Defines a layout that can be shared across different routes. It's akin to the framework of your house, providing a consistent structure and appearance.

- **Global Styles**: The `app/` directory also contains `global.css`, which applies styles globally across your application. If you're familiar with the 7-1 pattern from SASS, you might choose to organize your CSS files similarly here, enhancing modularity and maintainability.

## The `public/` Directory

The `public/` directory serves as the home for static assets such as images, fonts, and icons. Notably, placing an `icon.png` or `favicon.ico` in this directory automatically sets it as the website's favicon, streamlining the process of customizing your site's browser icon.

## Cleaning Up and Customization

As you get acquainted with your Next.js project, you may find files or directories that aren't necessary for your application's current scope. Removing these not only declutters your workspace but also simplifies your project structure, making it easier to navigate and maintain.

- **Deleting Unnecessary Files**: Initially, your Next.js project may include sample files or directories. Feel free to delete these to keep your project lean and relevant to your development goals.

## Exploring `package.json`

The `package.json` file in the root directory is crucial for managing your project's dependencies, scripts, and general metadata. One important script to note is `npm run dev`, which starts the development server, allowing you to preview your application locally.

- **Start Command**: Take a moment to review the `scripts` section of `package.json`. The `dev` script is particularly important for your development workflow, enabling you to start a local server for development purposes.

## Creating a "Hello World" App

With a clearer understanding of the Next.js project structure, let's simplify our application to a basic "Hello World":

1. **Simplify Your Application**: Remove any unnecessary files or components from the `app/` directory, leaving just the essentials for a basic application.
2. **Edit `page.js`**: Modify the `page.js` in your `app/` directory to include a simple greeting, showcasing the most straightforward form of a Next.js application.

   ```jsx
   export default function HomePage() {
     return <div>Hello, World!</div>;
   }
   ```

3. **View Your Changes**: Start your development server with `npm run dev` and navigate to `http://localhost:3000` to see your "Hello World" application in action.

By the end of this session, you should have a basic understanding of the Next.js file structure and how to begin customizing your project for your specific development needs.
