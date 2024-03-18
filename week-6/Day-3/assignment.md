# Assignment: Firebase Assignment 3

## Objective

To integrate Firestore into a Next.js application, demonstrating the ability to add new data to Firestore and display this data within the application. This exercise focuses on initializing Firestore, simple data modeling, and executing create and read operations.

## Instructions

### Part 1: Firestore Setup

1. **Initialize Firestore** in your Next.js project according to the provided demo code instructions. Ensure Firestore is correctly configured in a `firebaseConfig.js` file.

### Part 2: Adding Data to Firestore

1. **Develop a `SimpleForm` Component**: This component should include input fields for at least two pieces of data (e.g., a user's name and message). Implement the functionality to add a new document to a Firestore collection upon form submission. You may name the collection as you wish, such as `messages`.

### Part 3: Displaying Data from Firestore

1. **Create a `DataDisplay` Component**: This component is responsible for fetching documents from the Firestore collection used in `SimpleForm` and displaying the data in a list or another appropriate format.

### Part 4: Documentation and Submission

1. **Logging and README.md**:

   - Ensure successful document additions to Firestore are confirmed via console logging (e.g., "Document added with ID: XYZ").
   - Update the `README.md` file with a brief explanation of your integration process, challenges encountered, and their resolutions.

2. **Submission**:
   - Submit the URL of your GitHub repository containing your project code, including the `SimpleForm` and `DataDisplay` components. Your `README.md` should accurately describe your work on this assignment.

## Evaluation Rubric

Your assignment will be graded based on the following criteria, with a total of 25 points:

1. **Firestore Initialization (5 points)**:

   - **Complete (5 pts)**: Firestore is correctly initialized and configured within the Next.js project.
   - **Partial (3 pts)**: Firestore is initialized with minor issues in configuration.
   - **Limited (0 pts)**: Firestore is not correctly initialized or is missing.

2. **Functionality of `SimpleForm` Component (10 points)**:

   - **Complete (5 pts)**: The form correctly adds data to the Firestore collection, with appropriate handling of form submission.
   - **Partial (3 pts)**: The form adds data to Firestore with some issues in data handling or form submission.
   - **Limited (0 pts)**: The form does not add data to Firestore or is non-functional.

3. **Functionality of `DataDisplay` Component (10 points)**:
   - **Complete (5 pts)**: Data from Firestore is correctly fetched and displayed in the application.
   - **Partial (3 pts)**: Data is fetched from Firestore but with issues in display or data handling.
   - **Limited (0 pts)**: Data is not fetched or displayed from Firestore.

**Total**: 25 points
