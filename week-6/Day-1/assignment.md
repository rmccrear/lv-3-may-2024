# Assignment: Firebase Integration Assignment 6

## Objective

Demonstrate your understanding of integrating Firebase into a Next.js application by setting up Firebase Authentication with Google Sign-In and managing user sessions.

## Instructions

### Part 1: Setup Firebase and Next.js

1. **Initialize a Next.js Project**:

   - Use `create-next-app` to create a new Next.js project named `firebase-next-auth`.
   - Organize your application code within the `/src/app` directory.

2. **Create a Firebase Project**:

   - Go to the Firebase Console, create a new Firebase project, and note your project's configuration settings.

3. **Install Firebase SDK**:
   - In your Next.js project, install the Firebase package by running `npm install firebase`.

### Part 2: Configure Firebase Authentication

1. **Enable Google Sign-In**:

   - In the Firebase Console, navigate to the Authentication section and enable Google as a sign-in method.

2. **Set Up Firebase Configuration**:
   - Create a `firebaseConfig.js` file in your project to store your Firebase configuration.
   - Initialize Firebase in your project using these settings.

### Part 3: Implement Google Sign-In

1. **Authentication Module**:

   - Create a `firebaseAuth.js` file to handle authentication logic, including the `signInWithGoogle` function.

2. **Sign-In Button**:
   - Implement a Sign-In button in your application that calls `signInWithGoogle` when clicked.

### Part 4: Managing User Sessions

1. **Authentication State Listener**:

   - Set up an observer in your application to listen for changes in the authentication state (e.g., user logs in or out).
     Example observer:

   ```js
   import { getAuth, onAuthStateChanged } from 'firebase/auth';

   const auth = getAuth();

   const authStateListener = () => {
     onAuthStateChanged(auth, (user) => {
       if (user) {
         console.log(`User logged in: ${user.email}`);
       } else {
         console.log('User logged out');
       }
     });
   };

   export default authStateListener;
   ```

2. **Display User Information**:
   - Upon successful sign-in, display the user's name and email address on the page.

### Part 5: Documentation

1. **README.md**:
   - Document the steps for setting up the project, including how to configure Firebase and enable Google Sign-In.
   - Provide instructions on how to run your Next.js application.

## Submission

- **GitHub Repository**: Push your complete Next.js project to a new GitHub repository. Ensure that your `README.md` is comprehensive and well-organized.
- **Live Demo (Optional)**: If possible, deploy your Next.js application to Vercel or a similar platform and include the live demo link in your submission.
- **Repository URL**: Submit the URL of your GitHub repository as your assignment deliverable.

## Rubric

### Firebase and Next.js Setup - 5 points

- **Complete (5 pts)**: Successfully integrated Firebase into the Next.js project with a clear and logical setup.
- **Partial (3 pts)**: Firebase is integrated, but the setup has minor issues or lacks optimization.
- **Limited (1 pt)**: Failed to correctly integrate Firebase into the Next.js project.

### Google Sign-In Implementation - 5 points

- **Complete (5 pts)**: Google Sign-In is correctly implemented and functional.
- **Partial (3 pts)**: Google Sign-In is implemented but with minor issues or lacks user feedback.
- **Limited (1 pt)**: Google Sign-In is not implemented correctly or does not work.

### User Session Management - 5 points

- **Complete (5 pts)**: Effectively manages user sessions, with appropriate handling of authentication state changes.
- **Partial (3 pts)**: Manages user sessions but with room for improvement in state handling or user feedback.
- **Limited (1 pt)**: Inadequate management of user sessions or significant issues in handling authentication states.

### Code Quality and Best Practices - 5 points

- **Complete (5 pts)**: Code is clean, well-organized, and follows best practices for Firebase and Next.js development.
- **Partial (3 pts)**: Code is generally good but could be improved in terms of organization or adherence to best practices.
- **Limited (1 pt)**: Code is poorly organized, difficult to read, or does not follow best practices.

### Documentation and Deployment - 5 points

- **Complete (5 pts)**: Comprehensive documentation in `README.md` and, if applicable, successful deployment with a live demo.
- **Partial (3 pts)**: Documentation is adequate, but lacks details or clarity; deployment is attempted but may have minor issues.
- **Limited (1 pt)**: Documentation is sparse or unclear; failed to deploy or did not attempt deployment.
