### Goals and Objectives:

By the end of this tutorial, you will:
1. Set up a **Next.js** project from scratch.
2. Integrate **Tailwind CSS** into the project for styling.
3. Gain practical experience with **Next.js** and **Tailwind CSS** by creating a splash page.
4. Develop a basic understanding of setting up and testing a project workflow.
5. Build the habit of testing your work as you progress.

---

### Setup Instructions:

The following steps will guide you through creating a Next.js app and adding Tailwind CSS for styling. Please ensure you test after each step, and if you encounter any issues, don't hesitate to ask for help after spending 10-15 minutes troubleshooting.

#### Step 1: Create a Next.js Project
1. Open your terminal and run the following command to create a new Next.js project:
   ```bash
   npx create-next-app@latest
   ```

Choose the following options:

- TypeScript: No
- ESLint: Yes
- Tailwind CSS: Yes
- Use src/ directory: Yes
- Use App Router: No
- Customize import alias: No



#### Step 1 (Test):
1. Navigate into your project directory using:
   ```bash
   cd <project-directory>
   ```
2. Start the development server:
   ```bash
   npm run dev
   ```
3. Open `http://localhost:3000` in your browser. You should see the default Next.js landing page.

#### Step 2: Create a Home Component
1. Delete the contents of the `src/pages/index.js` file.
2. Replace it with a simple `Home` component as shown below:
   ```javascript
   // src/pages/index.js
   export default function Home() {
     return <h1>Welcome to the Cat App!</h1>;
   }
   ```

#### Step 2 (Test):
1. Visit `http://localhost:3000` in your browser. You should now see the message "Welcome to the Cat App!".

#### Step 3: Add Tailwind CSS to Your Project
1. ~~Follow the official Next.js Tailwind CSS installation guide to add Tailwind CSS to your project: [Tailwind CSS Next.js Setup Guide](https://tailwindcss.com/docs/guides/nextjs).~~ (This will already be configured for you if you selected the Tailwind CSS option during project creation.)

#### Step 3 (Test):
1. Add a Tailwind CSS class to the `h1` element in `src/pages/index.js`:
   ```javascript
   // src/pages/index.js
   export default function Home() {
     return <h1 className="text-4xl text-center">Welcome to the Cat App!</h1>;
   }
   ```
2. Reload your browser and confirm that the new Tailwind styles are applied to the heading.

#### Step 4: Create a Splash Page with Tailwind CSS
1. Use Tailwind CSS classes to enhance the look of your splash page.
2. Experiment with different Tailwind classes to style your `Home` component without writing custom CSS. For example, you can add spacing, colors, and layout utilities to make the page more visually appealing.

---

### What You Have Learned:

In this exercise, you have learned how to:
- Set up a **Next.js** project from scratch.
- Integrate **Tailwind CSS** for easy and fast styling.
- Create and modify a basic splash page using only Tailwind CSS classes, avoiding the need for custom CSS.
- Troubleshoot and test your code incrementally, improving your ability to build projects step-by-step.

This setup process forms a strong foundation for future Next.js projects with Tailwind CSS, allowing you to create modern, responsive web applications quickly.

You may refer back to this tutorial whenever you need to set up a new Next.js project with Tailwind CSS.

### Rubric

(20 points)

1. **Project Setup** (5 points)
   - The Next.js project was created successfully.
   - The development server started without errors.
2. **Home Component** (5 points)
   - The `Home` component was created and displayed the correct message.
   - The message was styled using Tailwind CSS classes.
3. **Tailwind CSS Integration** (5 points)
   - Tailwind CSS was successfully integrated into the project.
   - The `Home` component used Tailwind CSS classes for styling.
4. **Splash Page Styling** (5 points)
   - The splash page was styled using various Tailwind CSS classes.
   - The styling enhanced the visual appeal of the page.