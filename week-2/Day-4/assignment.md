# Assignment: Next.js Assignment 4

## Objective

This assignment focuses on enhancing your ability to create dynamic and interactive user interfaces with React. You'll be employing conditional rendering, managing props, and leveraging Next.js for client-side navigation. Your goal is to construct a user profile page that can dynamically display information and navigate through different profile sections efficiently.

## Instructions

### Part 1: Setting Up the User Profile Component

1. **Creating the UserProfile Component**:

   - Start by creating a new directory named `profile` within `src/app` to represent the user profile page's URL path.
   - Inside the `profile` directory, create a file named `page.js`. This will act as the entry point (like an index file) for your profile route.
   - Define a component named `UserProfile` in `page.js` that will display user information such as name, biography, and a list of hobbies. This data should be accepted as props.

2. **Implementing Conditional Rendering**:
   - In the `UserProfile` component, use conditional rendering techniques to display a placeholder text ("No biography available") if the biography prop is not provided.

### Part 2: Dynamically Displaying Hobbies

1. **Displaying the Hobbies List**:
   - The `UserProfile` component should also accept a list of hobbies as props. Utilize the `map` function to render each hobby in an unordered list.
   - If the hobbies list is empty, display a fallback message, such as "No hobbies listed."

### Part 3: Navigation and Layout

1. **Setting Up Client-Side Navigation**:

   - Create a navigation bar component that facilitates moving between the 'Home' page and the 'User Profile' page without full page reloads. Use the `Link` component from Next.js for creating navigation links.

2. **Configuring Home and Profile Pages**:
   - Ensure you have a `Home` page set up at the path `src/app/home/page.js`.
   - Include the navigation bar on both the Home and Profile pages to enable seamless navigation.

### Part 4: Simulating User Data Fetching

1. **Fetching User Data on the Profile Page**:
   - On the 'User Profile' page (`profile/page.js`), simulate fetching user data by defining a user object within the page. Then, pass this object as props to the `UserProfile` component.

### Part 5: GitHub Repository Update

- **Committing and Pushing Changes**:
  - Make sure all changes are committed to your Git repository with clear and descriptive commit messages. Push these commits to your GitHub repository.

### Part 6: Submission

- **Submitting Your Work**:
  - Submit the URL of your GitHub repository containing the Next.js application as your assignment deliverable.

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
