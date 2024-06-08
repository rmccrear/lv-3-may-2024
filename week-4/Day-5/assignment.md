# Assignment: Firebase Assignment 5

## Objective

Build upon the real-time application created in Firebase Assignment 5 by incorporating update and delete functionalities, along with applying basic styling to enhance the user interface. This assignment aims to deepen your understanding of CRUD operations within a real-time Firestore context and improve the overall user experience of your application.

## Instructions

### Part 1: Enhance `RealTimeForm` and `RealTimeDisplay` Components

1. **Refine `RealTimeForm` Component**:

   - If not already implemented, add fields that allow for the updating of existing documents in your Firestore collection.
   - Implement a mechanism to select a document for updating, such as a dropdown or a list from which a user can choose an entry to edit.

2. **Update `RealTimeDisplay` Component for Deletion**:
   - Integrate a delete button or icon next to each displayed document.
   - Implement the functionality to delete the document from Firestore in real-time when this button or icon is clicked.

### Part 2: Implement Real-Time Document Updating

1. **Create an `UpdateDocumentForm` Component** (if separate from your `RealTimeForm`):
   - This component should enable users to update fields of existing documents within your Firestore collection.
   - Reflect changes in real-time in the `RealTimeDisplay` component upon submission.

### Part 3: Style Your Application

1. **Apply Basic Styling**:
   - Use CSS modules, styled-components, or another CSS-in-JS library to style your components.
   - Focus on creating a user-friendly interface that makes it clear how to add, update, and delete documents.
