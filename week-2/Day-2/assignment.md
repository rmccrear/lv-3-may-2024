# Assignment: Next.js Assignment 2

## Objective

The purpose of this assignment is to deepen your understanding of state management in React using the `useState` hook. You will build two components: a counter that can increase, decrease, and reset its value, and a form that captures user input in a controlled manner. This exercise will reinforce the concepts of stateful logic in functional components and demonstrate the power of React's reactivity system.

## Instructions

### Part 1: Counter Component

1. **Create the Counter Component**:

   - In your Next.js project's `components` directory, create a file named `Counter.js`.
   - Implement a counter with three buttons to increase, decrease, and reset its value, as shown in the provided example.

2. **Integrate the Counter in Your Application**:
   - Import and render the `Counter` component in your `src/app/page.js` file.

### Part 2: Controlled Form Component

1. **Set Up the User Form Component**:

   - Create a new file named `UserForm.js` in the `components` directory.
   - Design a form with a single text input field for the user's name and a submit button. The form should display the input value using an alert upon submission.

2. **Implement Controlled Component Logic**:

   - Utilize the `useState` hook to manage the input field's state, ensuring the input is a controlled component.
   - Include functions to handle changes to the input field and the form submission, as outlined in the example.

3. **Display the Form in Your Application**:
   - Import and include the `UserForm` component on a new page in your Next.js project, or on the existing `page.js` page.

### Part 3: GitHub Repository Update

- **Commit Your Changes**:
  - Ensure all changes are committed to your Git repository with descriptive commit messages.
- **Push to GitHub**:
  - Push your latest commits to your GitHub repository to update your project online.

### Part 4: Submission

- **Submit Your GitHub Repository URL**:
  - Provide the URL to your GitHub repository containing the updated project with the `Counter` and `UserForm` components.

## Rubric

### Node.js Installation and Verification - 5 points

- **Complete (5 pts)**: Demonstrates correct usage and understanding of the `useState` hook in both components, with the project successfully running.
- **Partial (3 pts)**: Components use `useState` but have minor issues in functionality or implementation.
- **Limited (0 pts)**: Misuse of `useState` hook or components fail to function as intended.

### GitHub Repository Setup - 5 points

- **Complete (5 pts)**: Repository is updated with the latest code for the counter and form components, including clear commit messages.
- **Partial (3 pts)**: Repository is updated but lacks clear commit messages or has incomplete implementation of one component.
- **Limited (0 pts)**: Did not update the repository or the update does not include the required components.

### Script Execution - 5 points

- **Complete (5 pts)**: Both the counter and form components execute correctly, reflecting an understanding of state management and controlled components.
- **Partial (3 pts)**: Minor errors in component execution or functionality.
- **Limited (0 pts)**: Significant issues prevent component execution or functionality.

### Documentation in README.md - 5 points

- **Complete (5 pts)**: README.md clearly documents the purpose and functionality of the counter and form components, including how to run the project.
- **Partial (3 pts)**: README.md is updated but lacks details on component functionality or project execution.
- **Limited (0 pts)**: README.md is not updated to reflect the addition of the counter and form components.

### Submission Completeness - 5 points

- **Complete (5 pts)**: Provides a link to the fully updated GitHub repository, demonstrating a comprehensive understanding of React state management.
- **Partial (3 pts)**: GitHub link provided, but the repository lacks comprehensive documentation or complete implementation of both components.
- **Limited (0 pts)**: Fails to provide a GitHub link, or the repository does not meet the assignment requirements.
