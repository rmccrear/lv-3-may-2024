# Assignment: Firebase Assignment 2

## Objective

To reinforce your understanding of Firebase Authentication within a Next.js application by incorporating comprehensive authentication mechanisms, managing user sessions, and implementing access control through protected routes.

## Instructions

### Part 1: Authentication Enhancement

- **Implement Email/Password Authentication:** Create a form that allows users to sign in using their email and password. This form should provide feedback in case of an incorrect email or password.
- **Integrate Google Sign-In:** Add a "Sign in with Google" button to your application. Document the steps taken in the Firebase Console to enable Google Sign-In with screenshots included in your README.md.

### Part 2: User Session Management

- **Manage Authentication State:** Utilize React's `useState` and `useEffect` hooks to track and display the user's authentication state. Show the user's email upon successful login and implement a logout button.
- **Session Persistence:** Ensure that the user's authentication state persists across page reloads and navigations within your application.

### Part 3: Secure Routes

- **Protected Page Creation:** Develop a page that is only accessible to authenticated users. If an unauthenticated user attempts to access this page, redirect them to the login page.
- **Conditional UI Rendering:** Use conditional rendering based on the user's authentication status to show or hide elements related to user information.

### Submission

- Commit your code to a GitHub repository.
- Include a README.md in your repository detailing:
  - The steps to run your application.
  - A brief explanation of how you implemented the functionalities.
  - Screenshots showing the login page, the protected page accessible only when logged in, and the application displaying the user's email.

## Evaluation Rubric

Assignments will be graded based on the following criteria, with each criterion worth 5 points for a total of 25 points:

**Firebase Email/Password Authentication Implementation (5 Points)**

- Complete: All features implemented correctly.
- Partial: Missing some functionalities or minor issues.
- Limited: Significant functionalities missing or incorrect.

**Google Sign-In Integration and Documentation (5 Points)**

- Complete: Integration successful with detailed documentation.
- Partial: Integration with incomplete documentation.
- Limited: Integration unsuccessful or not attempted.

**User Session Management (5 Points)**

- Complete: User sessions are correctly managed and persistent.
- Partial: User sessions mostly work with some minor issues.
- Limited: User sessions are not managed correctly or not implemented.

**Protected Routes Implementation (5 Points)**

- Complete: Protected routes correctly redirect based on user status.
- Partial: Some issues with redirecting or route protection.
- Limited: Protected routes not implemented or working incorrectly.

**Documentation and README.md Completeness (5 Points)**

- Complete: README.md is detailed with explanations and screenshots.
- Partial: README.md is present but lacks some information or clarity.
- Limited: README.md is missing, very incomplete, or unclear.
