# Assignment: Next.js Assignment 3

## Objective

This assignment aims to deepen your understanding of the `useEffect` hook in React by applying it to a practical scenario: fetching data from the Star Wars API (SWAPI). You will create a component that fetches character data, displays this data, and incorporates loading states and error handling to manage the fetch operation's various states effectively.

## Instructions

### Part 1: Fetching Data with `useEffect`

1. **Create a New Component**:

   - install `axios` with `npm i axios`
   - In your project's `components` directory, create a file named `StarWarsCharacter.js`.
   - This component will be responsible for fetching data about a specific Star Wars character from the SWAPI.

2. **Implement Data Fetching Logic**:
   - Use the `useEffect` hook to initiate the data fetch when the component mounts.
   - Fetch character data from `https://swapi.dev/api/people/{id}/`, where `{id}` is the ID of a Star Wars character you choose.
   - Manage the fetched data's state, the loading state, and any errors that might occur during the fetch operation using `useState`.

### Part 2: Managing Loading and Error States

1. **Implement Loading State**:

   - Introduce a boolean state variable to track the loading status of the API request.
   - While data is being fetched, display a "Loading..." message in your component.

2. **Implement Error Handling**:
   - Use a try-catch block inside your data fetching function to handle any errors during the fetch operation.
   - Store any errors in a state variable, and display an error message in your component if an error is caught.

### Part 3: Displaying Fetched Data

- Once the data is successfully fetched and the component's state is updated, display the Star Wars character's name and any other relevant information you wish to include (e.g., birth year, eye color).

### Part 4: GitHub Repository Update

- **Commit Your Changes**:
  - Make sure all changes are committed to your Git repository with descriptive commit messages.
- **Push to GitHub**:
  - Push your latest commits to your GitHub repository to ensure your project is up-to-date online.

### Part 5: Submission

- **Submit Your GitHub Repository URL**:
  - Provide the URL to your GitHub repository that contains the `StarWarsCharacter` component as your assignment submission.

## Rubric

### Node.js Installation and Verification - 5 points

- **Complete (5 pts)**: Successfully implements the `useEffect` hook for fetching data from the Star Wars API, with correct management of loading and error states.
- **Partial (3 pts)**: Uses `useEffect` and `useState` hooks with minor issues in loading or error handling.
- **Limited (0 pts)**: Incorrect or incomplete use of `useEffect`, `useState`, or missing key functionalities.

### GitHub Repository Setup - 5 points

- **Complete (5 pts)**: The repository is updated with the latest code for the `StarWarsCharacter` component, including clear and descriptive commit messages.
- **Partial (3 pts)**: The repository is updated but has unclear commit messages or incomplete implementation.
- **Limited (0 pts)**: Did not update the repository or the update does not include the `StarWarsCharacter` component.

### Script Execution - 5 points

- **Complete (5 pts)**: The `StarWarsCharacter` component correctly fetches and displays data, manages loading and error states effectively.
- **Partial (3 pts)**: The component has issues with data display, loading, or error handling but partially works.
- **Limited (0 pts)**: Significant functionality issues prevent the component from operating correctly.

### Documentation in README.md - 5 points

- **Complete (5 pts)**: The `README.md` clearly documents the purpose and functionality of the `StarWarsCharacter` component, including instructions on running the project.
- **Partial (3 pts)**: The `README.md` is updated but lacks detail about the component's functionality or how to run the project.
- **Limited (0 pts)**: The `README.md` is not updated to reflect the addition of the `StarWarsCharacter` component.

### Submission Completeness - 5 points

- **Complete (5 pts)**: Provides a link to the fully updated GitHub repository, showing a comprehensive understanding of React hooks, especially `useEffect`.
- **Partial (3 pts)**: The GitHub link is provided, but the repository lacks comprehensive documentation or complete implementation of the `StarWarsCharacter` component.
- **Limited (0 pts)**: Fails to provide a GitHub link, or the repository does not meet the assignment's requirements.
