# Assignment: Firebase Assignment 1 - Setup and Authentication

## Objective

Leverage Firebase to enhance a Next.js application with real-time capabilities and authentication. You'll set up Firebase in a Next.js project, implement Google Sign-In authentication, and handle user sessions.

## Instructions

### Part 1: Firebase Setup

1. **Firebase Project**: Create a Firebase project through the Firebase Console. Document the process with screenshots, specifically highlighting the creation of the project and enabling Google Analytics.

2. **Firebase SDK Installation**: Integrate Firebase into your Next.js application by installing the Firebase package. Use the provided `npm install firebase` command in your project directory.

3. **Firebase Configuration**:
   - Create a `firebaseConfig.js` file in your project. Store your Firebase project's configuration in this file.
   - Initialize Firebase in your application. Refer to the demo code on creating an `initFirebase.js` file. Ensure it checks for an existing Firebase instance before initialization.

### Part 2: Implementing Authentication

1. **Google Sign-In**:

   - Set up Google Sign-In method in your Firebase project. Capture this process with screenshots.
   - Implement a "Sign in with Google" button in your application that utilizes Firebase Authentication to sign in users.
   - Use the `firebaseAuth.js` module from the demo code as a reference.

2. **Session Handling**:
   - Implement functionality to observe the user's authentication state (signed in/out). Use the `useAuth` hook pattern provided in the demo code.
   - Display the user's name on the application's main page upon successful sign-in. If signed out, show a message indicating the user is not signed in.

### Part 3: Documentation and Submission

- **Console Log and README.md**:

  - Ensure actions such as signing in and signing out are logged to the console.
  - Capture a successful sign-in screen as a screenshot. Include this image in your `README.md`.
  - Update your `README.md` with a brief explanation of your implementation process, highlighting how you integrated Firebase and managed user authentication.

- **Submission**:
  - Push your code to a GitHub repository. Include a link to the repository and ensure it contains your updated `README.md` with the required screenshots and explanations.

## Evaluation Rubric

Your assignment will be graded on the following criteria, with a total of 25 points:

1. **Firebase Integration (5 points)**:

   - Complete (5 points): Correct installation and initialization of Firebase in the Next.js project.
   - Partial (3 points): Firebase is installed but not properly initialized.
   - Limited (0 points): Firebase installation or initialization is missing.

2. **Authentication Implementation (10 points)**:

   - Complete (5 points): Successful implementation of Google Sign-In, including UI component for signing in and correct handling of authentication state changes.
   - Partial (3 points): Google Sign-In implemented with minor issues in handling authentication states or UI.
   - Limited (0 points): Google Sign-In not implemented or non-functional.

3. **Documentation and Submission Completeness (10 points)**:
   - Complete (5 points): Detailed `README.md` with process explanation, console logs for sign-in/sign-out actions, and a screenshot of a successful sign-in.
   - Partial (3 points): `README.md` is present but lacks detail or missing console logs/screenshot.
   - Limited (0 points): `README.md` is missing or does not describe the assignment implementation.
