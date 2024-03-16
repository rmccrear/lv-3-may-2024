# Assignment: Next.js Assignment 4

## Objective

This assignment is designed to reinforce your skills in creating dynamic user interfaces with React, utilizing conditional rendering, props, and client-side navigation with Next.js. Instead of replicating the demo code, you will apply these concepts in a new context. You will build a user profile page that dynamically displays user information and includes navigation to different sections of the profile.

## Instructions

### Part 1: User Profile Setup

1. **Create a User Profile Component**:

   - Name your component `UserProfile`. It should display a user's name, biography, and a list of hobbies. This information will be passed as props to the component.

2. **Implement Conditional Rendering**:
   - Within the `UserProfile` component, use conditional rendering to display a message if the user's biography is not provided. For example, "No biography available".

### Part 2: Dynamic Hobbies List

1. **Rendering the Hobbies List**:
   - Pass a list of hobbies to the `UserProfile` component as props. Use the `map` function to display each hobby as an item in an unordered list.
   - If the list of hobbies is empty, display a message like "No hobbies listed".

### Part 3: Navigation and Page Layout

1. **Implement Client-Side Navigation**:

   - Create a simple navigation bar component that allows the user to navigate between the 'Home' page and the 'User Profile' page without reloading the page. Use the `Link` component from Next.js for navigation links.

2. **Create a Home Page and Profile Page**:
   - Set up two pages in your Next.js app: `index.js` (Home) and `profile.js` (User Profile).
   - Include the navigation bar in both pages to allow easy navigation between them.

### Part 4: Fetching User Data

1. **Simulate Fetching User Data**:
   - On the 'User Profile' page, simulate fetching user data (e.g., name, biography, hobbies) by defining a user object and passing it as props to the `UserProfile` component.

### Part 5: GitHub Repository Update

- **Commit and Push Your Changes**:
  - Ensure all your changes are committed with clear, descriptive messages. Push the commits to your GitHub repository.

### Part 6: Submission

- **Submit Your GitHub Repository URL**:
  - Provide the URL to your GitHub repository that contains your Next.js application as your submission for this assignment.

## Rubric

### Node.js Installation and Verification - 5 points

- **Complete (5 pts)**: The application demonstrates effective use of conditional rendering, props for data passing, and client-side navigation with clear understanding and application of concepts.
- **Partial (3 pts)**: Minor issues in applying conditional rendering, props, or client-side navigation, but demonstrates basic understanding.
- **Limited (0 pts)**: Significant misunderstanding or incorrect application of conditional rendering, props, or client-side navigation.

### GitHub Repository Setup - 5 points

- **Complete (5 pts)**: Repository is well-organized with the complete project and descriptive commit messages.
- **Partial (3 pts)**: Repository contains the project, but commit messages lack clarity or parts of the project are incomplete.
- **Limited (0 pts)**: Repository setup is incorrect, incomplete, or lacks significant portions of the assignment.

### Script Execution - 5 points

- **Complete (5 pts)**: Application runs successfully, showcasing a dynamic user profile with implemented features according to the assignment instructions.
- **Partial (3 pts)**: Application runs with minor errors or omissions in features.
- **Limited (0 pts)**: Application has significant execution errors, preventing it from running as intended.

### Documentation in README.md - 5 points

- **Complete (5 pts)**: `README.md` is comprehensive, detailing project setup, how to run the application, and an overview of implemented features.
- **Partial (3 pts)**: `README.md` is present but lacks detail on setup, execution, or feature overview.
- **Limited (0 pts)**: Inadequate documentation in `README.md` or documentation is missing critical information.

### Submission Completeness - 5 points

- **Complete (5 pts)**: Submission includes a link to a fully updated and complete GitHub repository, reflecting a deep understanding and application of the assignment's objectives.
- **Partial (3 pts)**: GitHub link provided, but the repository is missing some aspects of the assignment's objectives or depth in implementation.
- **Limited (0 pts)**: Fails to provide a GitHub link, or the repository does not meet the basic requirements of the assignment.
