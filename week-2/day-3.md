### Coding Bootcamp Assignment: Building a Counter in Next.js

#### Objective:
In this assignment, you will create a simple **counter application** using **Next.js**. The counter should be able to increment and decrement, with the functionality and state managed within a new page.

---

### Problem Statement:

You are tasked with building a basic counter application in **Next.js**. The counter should be displayed on a new page within the Next.js app, with buttons to increase and decrease the count.

This exercise will help you understand how to create new pages in Next.js, manage state, and handle user events.

---

### Requirements:

1. **Create a New Page in Next.js**:
   - Add a new page to the Next.js application. Name the page something appropriate (e.g., `/counter`).
   
2. **Display the Counter**:
   - The counter starts at 0 and should be displayed on the `/counter` page.

3. **Increment Button**:
   - Add an "Increment" button.
   - When clicked, the button should increase the counter value by 1.

4. **Decrement Button**:
   - Add a "Decrement" button.
   - When clicked, the button should decrease the counter value by 1.
   
5. **Prevent Negative Values**:
   - The counter should not go below 0. Ensure that the user cannot decrement the counter into negative numbers.

---

### Steps to Complete:

1. **Set Up a New Next.js Project**:
   - Use the following commands to set up a new Next.js project:
     ```bash
     npx create-next-app@latest counter-app
     cd counter-app
     npm run dev
     ```
   - Open the project in your code editor.

2. **Create a New Page**:
   - Inside the `pages` directory, create a new file called `counter.js`.
   - This page will hold your counter component and the logic for incrementing and decrementing.

3. **Manage State**:
   - Use the React `useState` hook to manage the counter's state.
   - Initialize the counter state at 0.

4. **Add Increment and Decrement Buttons**:
   - Add two buttons to the page for incrementing and decrementing the counter.
   - Use the `onClick` event handler to modify the state when the buttons are clicked.

5. **Prevent Counter from Going Below Zero**:
   - Ensure that the counter does not go below 0. If the counter is at 0, the decrement button should either do nothing or be disabled.

6. **Style the Page** (Optional):
   - You can add simple styles to make the counter and buttons look better, but the primary focus is on functionality.

---

### Stretch Goals (Optional):

1. **Reset Button**:
   - Add a "Reset" button to reset the counter back to 0 when clicked.

2. **Custom Step Input**:
   - Allow the user to input a custom step value, so that the counter increments or decrements by a user-defined value instead of just 1.

3. **Double Increment/Decrement**:
   - Add "Double Increment" and "Double Decrement" buttons to increase or decrease the counter by 2 at a time.

---

### Submission Guidelines:

1. **Create a GitHub Repository**:
   - Create a GitHub repository for your project. Name it something appropriate, like `nextjs-counter-app`.

2. **Push Your Code**:
   - Push your completed code to the repository.

3. **Turn In the Assignment**:
   - Submit the **link to your GitHub repository** in the class Moodle.

---

### Example Workflow:

1. **Run the Next.js Development Server**:
   - Start the development server to see your changes live:
     ```bash
     npm run dev
     ```

2. **Test the Counter**:
   - Visit the `/counter` page to ensure the counter works correctly.
   - Check that the increment and decrement functionality works and that the counter doesn't go below 0.

3. **Deploy to GitHub**:
   - Once you're happy with your counter app, push it to GitHub using the following commands:
     ```bash
     git init
     git add .
     git commit -m "Initial commit for Next.js counter app"
     git remote add origin <your-github-repository-url>
     git push -u origin main
     ```

4. **Submit on Moodle**:
   - Turn in the **GitHub repository link** on Moodle for review.

---

### Evaluation Criteria:

- Correct implementation of the counter functionality (increment, decrement, and preventing negative values).
- Use of the `useState` hook to manage state.
- The counter page should load correctly in Next.js as a separate page (`/counter`).
- Bonus points for any extra functionality (reset button, custom step input, etc.).
- Code should be clean, organized, and well-commented where necessary.

---

### Tips:

- Make sure to read the **Next.js documentation** on creating new pages if you're unsure how it works.
- Focus on getting the core functionality working first before moving on to any stretch goals or styling.
- Test your application thoroughly to ensure all requirements are met before pushing your code to GitHub.

Good luck, and happy coding!