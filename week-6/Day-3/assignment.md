# Assignment: Firestore Assignment 3 - CRUD Operations in Next.js

## Objective

Integrate Firestore into a Next.js application to perform CRUD (Create, Read, Update, Delete) operations. Build a simple todo application that allows users to add, view, update, and delete todo items.

## Instructions

### Part 1: Firestore Setup

1. **Initialize Firebase & Firestore**:

   - Ensure Firebase is installed and initialized in your Next.js project as previously instructed.
   - Enable Firestore in the Firebase Console and set up Firestore in test mode.

2. **Implement Firestore Configuration**:
   - Create a `firebaseConfig.js` file with Firebase initialization and export the Firestore database instance.

### Part 2: Implementing CRUD Operations

1. **Creating Todos**:

   - Implement an `addTodo` function in a utility file (e.g., `firestore.js`) that adds a new todo item to the Firestore `todos` collection.
   - Build a `TodoForm` component that includes form inputs for the todo title and description, and a button to submit the form. Use the `addTodo` function to create a new todo item when the form is submitted.

2. **Reading Todos**:

   - Create a `TodoList` component that fetches all todo items from the Firestore `todos` collection on component mount. Display each todo item in a list, including the title and description.

3. **Updating Todos**:

   - Implement an `updateTodo` function that updates the title and description of an existing todo item based on its document ID.
   - Create an `UpdateTodo` form component that allows users to edit the title and description of a todo item. Use the `updateTodo` function to apply the changes to Firestore.

4. **Deleting Todos**:
   - Implement a `deleteTodo` function that removes a todo item from the Firestore `todos` collection based on its document ID.
   - Build a `DeleteTodoButton` component that, when clicked, uses the `deleteTodo` function to remove a todo item from Firestore.

### Part 3: Displaying Todos

- Integrate the `TodoForm`, `TodoList`, `UpdateTodo`, and `DeleteTodoButton` components into your application's UI. Ensure that the list of todos updates in real-time when items are added, updated, or deleted.

### Part 4: Documentation and Submission

1. **Console Logging**:

   - Implement console logging within your CRUD functions to log actions (e.g., "Document written with ID:", "Document successfully updated!", "Document successfully deleted!") to the browser console.

2. **README.md**:

   - Document your process for integrating Firestore and performing CRUD operations in your README.md. Describe each component and function you created, including their purpose and how they interact with Firestore.
   - Include a section that explains the difference between SQL and NoSQL databases, based on your understanding and the provided resources.

3. **Submission**:
   - Submit the URL to your GitHub repository containing the Next.js project with Firestore integration. Ensure your repository is public and includes all the necessary files and an updated README.md.

## Evaluation Criteria

- Firestore setup and Firestore database initialization - 5 points
- Functionality of CRUD operations (Create, Read, Update, Delete) - 10 points
- Integration and real-time update of the UI components - 5 points
- Clarity and completeness of documentation in README.md - 5 points

**Total**: 25 points
