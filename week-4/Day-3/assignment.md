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

## Rubric

Your assignment will be graded based on the following criteria, each worth 5 points for a total of 25 points:

1. **Firestore Initialization (5 Points)**

   - **Complete (5 pts):** Firestore is correctly initialized and configured within the Next.js project.
   - **Partial (3 pts):** Firestore is initialized with minor issues in configuration.
   - **Limited (0 pts):** Firestore is not correctly initialized or is missing.

2. **Implementation of `SimpleForm` Component (5 Points)**

   - **Complete (5 pts):** The component effectively adds new data to Firestore, with data validation and feedback to the user upon submission.
   - **Partial (3 pts):** The component adds data to Firestore but lacks complete data validation or user feedback.
   - **Limited (0 pts):** The component fails to add data to Firestore or is significantly incomplete.

3. **Implementation of `DataDisplay` Component (5 Points)**

   - **Complete (5 pts):** Data from Firestore is accurately fetched and displayed, with appropriate UI considerations for data presentation.
   - **Partial (3 pts):** Data is fetched and displayed with minor issues in UI presentation or data fetching efficiency.
   - **Limited (0 pts):** The component does not fetch or display data correctly, or is substantially incomplete.

4. **Code Quality and Documentation (5 Points)**

   - **Complete (5 pts):** Code is well-organized, and well-documented with clear comments and a thorough README.md.
   - **Partial (3 pts):** Code and documentation are mostly complete with some areas lacking clarity or organization.
   - **Limited (0 pts):** Code is poorly organized or documented, with a README.md that does not effectively explain the project.

5. **Submission Completeness (5 Points)**
   - **Complete (5 pts):** All parts of the assignment are completed and submitted, including all required components and documentation.
   - **Partial (3 pts):** Most parts of the assignment are completed with minor missing elements.
   - **Limited (0 pts):** Significant portions of the assignment are incomplete or missing.
