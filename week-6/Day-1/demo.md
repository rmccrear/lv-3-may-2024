# Assignment: Firebase Assignment 1

## Objective

Implement Firebase Authentication with Google Sign-In in a Next.js application, manage user sessions, and demonstrate successful user authentication by logging user information to the console and including a screenshot in your submission.

## Instructions

### Part 1: Setup Firebase and Next.js

1. **Initialize a Next.js Project**:

   - Use `npx create-next-app@latest firebase-next-auth` to create a new Next.js project.
   - Structure your project to use a `/src` directory for your application code.

2. **Create and Configure a Firebase Project**:

   - Go to the Firebase Console, create a new project, and enable Google Analytics if desired.
   - In the Authentication section, enable Google as a sign-in method.
   - Install Firebase in your project with `npm install firebase`.

3. **Firebase Configuration**:
   - In your Next.js project, create `firebaseConfig.js` inside the `/src` directory and fill it with your Firebase project's settings.

### Part 2: Implement Google Sign-In

1. **Authentication Module Setup**:

   - Create `firebaseAuth.js` within `/src`. Implement `signInWithGoogle` to trigger Google Sign-In.
   - Upon successful sign-in, log the user's `displayName` and `email` to the console.

2. **UI Integration**:
   - Add a Sign-In button in your application that, when clicked, calls `signInWithGoogle`.
   - Style the button minimally to differentiate it from other elements on the page.

### Part 3: User Session Management

1. **Implement an Authentication State Observer**:

   - Use Firebase Authentication to set up an observer for user state changes.
   - On user login, log "User logged in: " followed by the user's `displayName` and `email`. On logout, log "User logged out".

2. **Display User Information**:
   - After login, display the user's `displayName` and `email` on the page.
   - Ensure this information is visible only when a user is logged in.

### Part 4: Documentation and Submission

1. **README.md**:

   - Clearly document the process of setting up Firebase in your Next.js project.
   - Include a section demonstrating the successful implementation with screenshots showing the console logs and user information display.
   - Provide instructions for running your project locally.

2. **Submission**:
   - Push your project to GitHub, making sure your `README.md` includes the required screenshots.
   - Submit the URL of your GitHub repository. Ensure your repository is public.

## Rubric

### Firebase Setup and Configuration - 5 points

- **Complete (5 pts)**: Firebase is correctly integrated, with detailed documentation of the setup process in `README.md`.
- **Partial (3 pts)**: Minor issues in Firebase integration or setup documentation lacks some details.
- **Limited (1 pt)**: Firebase integration is incorrect or undocumented.

### Google Sign-In Functionality - 5 points

- **Complete (5 pts)**: Google Sign-In is fully functional, with user information logged to the console as instructed.
- **Partial (3 pts)**: Google Sign-In works, but console logging is incomplete or incorrect.
- **Limited (1 pt)**: Google Sign-In is non-functional or not implemented.

### User Session Handling - 5 points

- **Complete (5 pts)**: User sessions are correctly managed, with clear console logging of user state changes.
- **Partial (3 pts)**: Basic user session management implemented but lacks full adherence to the assignment requirements.
- **Limited (1 pt)**: Poor handling of user sessions, with no or incorrect logging.

### UI Implementation and Code Quality - 5 points

- **Complete (5 pts)**: The Sign-In button and user information display are correctly implemented and styled, with high-quality code throughout the project.
- **Partial (3 pts)**: UI elements are present but could be improved; the code is generally good but may have some inconsistencies.
- **Limited (1 pt)**: UI elements for authentication are missing, poorly implemented, or not styled; code quality is low.

### Documentation and Evidence - 5 points

- **Complete (5 pts)**: Comprehensive `README.md` with clear setup instructions, screenshots of console logs, and user information display.
- **Partial (3 pts)**: Documentation is present but lacks clarity or misses screenshots.
- **Limited (1 pt)**: Inadequate documentation or absence of required screenshots.
