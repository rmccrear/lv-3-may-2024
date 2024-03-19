# Assignment: Firebase Assignment 4

## Objective

Enhance your Firebase and Next.js integration skills by recreating a project similar to Firebase Assignment 3, this time incorporating real-time data listening with Firestore. This assignment focuses on understanding and implementing live data synchronization within a Next.js application.

## Instructions

### Part 1: Initialize a New Next.js Project with Firestore

1. **Create a New Next.js Project**: Use `create-next-app` to initiate a new project setup.
2. **Setup Firebase and Firestore**: Install Firebase, set up a new Firebase project in the Firebase Console, and initialize Firebase in your Next.js project as shown in previous assignments.

### Part 2: Implement Real-Time Data Addition and Display

1. **Develop a `RealTimeForm` Component**:

   - This component should include input fields relevant to your chosen data model (e.g., a user's name and message).
   - Implement functionality to add new documents to a Firestore collection upon form submission. This collection can be named according to your data model, such as `realTimeMessages`.

2. **Create a `RealTimeDisplay` Component**:
   - This component is responsible for displaying documents from your Firestore collection.
   - Use Firestore's `onSnapshot` to subscribe to real-time updates from your collection, ensuring that any additions, updates, or deletions are instantly reflected in your application's UI.

### Part 3: Documentation and Submission

1. **Provide Detailed Code Comments**: Explain your code, especially the parts implementing real-time updates with Firestore's `onSnapshot`.
2. **Update README.md**:

   - Describe the process of setting up Firestore for real-time updates in your new Next.js project.
   - Include any challenges encountered during the implementation of real-time data operations and how they were resolved.

3. **Submission**:
   - Push your project to a GitHub repository.
   - Submit the URL of your repository, ensuring it contains the `RealTimeForm` and `RealTimeDisplay` components along with a detailed `README.md`.

## Evaluation Rubric

Each criterion is worth 5 points, for a total of 25 points:

1. **Firestore Real-Time Setup (5 points)**:

   - Complete: Successfully initialized Firestore and implemented real-time listening in the Next.js project.
   - Partial: Firestore is initialized, and real-time listening is implemented but with minor issues.
   - Limited: Failed to initialize Firestore for real-time listening or significant issues present.

2. **Functionality of `RealTimeForm` Component (5 points)**:

   - Complete: The component effectively adds new data to Firestore in real-time.
   - Partial: Adds data to Firestore but not reflecting in real-time accurately.
   - Limited: Fails to add data to Firestore or real-time functionality not implemented.

3. **Functionality of `RealTimeDisplay` Component (5 points)**:

   - Complete: Accurately displays real-time data updates from Firestore.
   - Partial: Displays data from Firestore but with issues in real-time synchronization.
   - Limited: Does not display real-time data updates from Firestore correctly.

4. **Code Quality and Comments (5 points)**:

   - Complete: Code is well-organized, clearly commented, especially on real-time aspects.
   - Partial: Mostly organized and commented but lacks clarity on real-time implementation.
   - Limited: Poor organization or lack of comments, unclear real-time data handling.

5. **Documentation in README.md (5 points)**:
   - Complete: README clearly documents the real-time Firestore setup and challenges resolved.
   - Partial: README documents the project but lacks detail on real-time implementation or challenges.
   - Limited: Incomplete README, missing documentation on real-time Firestore integration.
