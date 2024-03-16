# Assignment: Next.js Assignment 1

## Objective

The aim of this assignment is to familiarize you with the Next.js framework by creating a simple project. You'll learn to set up a new Next.js application, explore its file structure, and create a basic page. This introduction will help you understand how Next.js combines the power of React with additional features like server-side rendering and static site generation.

## Instructions

### Part 1: Setting Up Your Next.js Project

1. **Create a New Next.js Application**:

   - Run `npx create-next-app@latest your-project-name` in your terminal, replacing `your-project-name` with the desired name of your project.
   - Navigate into your project directory using `cd your-project-name`.

2. **Explore the Project Structure**:
   - Open the project in your preferred code editor and familiarize yourself with the file structure, especially the `app` and `public` directories.

### Part 2: Creating Your First Page

1. **Modify the Home Page**:

   - Navigate to `src/app/page.js`.
   - Replace the existing content with a simple custom message, such as a welcome message or your favorite quote.

2. **Add a New Page**:
   - Create a new file in the `app` directory named `about.js`.
   - In `about.js`, create a functional component that returns a brief about me page or any content you prefer.

### Part 3: Running Your Application

1. **Start the Development Server**:
   - Run `npm run dev` in your terminal to start the development server.
   - Open your browser and navigate to `http://localhost:3000` to view your home page, and `http://localhost:3000/about` to view your about page.

### Part 4: GitHub Repository Setup

1. **Initialize a GitHub Repository**:  
   **NOTE: CREATING A NEXT APP CREATES A LOCAL REPO, YOU WILL NEED TO PUSH YOUR REMOTE CODE TO GITHUB, NOT CLONE YOUR GITHUB REPO DOWN**

   **NOTE: DO NOT CREATE YOUR GITHUB REPO WITH A README**

   - Create a new repository on GitHub and follow the instructions to push your local repository to GitHub.

2. **Document Your Work**:
   - Update the `README.md` file to describe your project and the steps you followed to create it.
   - Include a screenshot of your browser showing the output of your Next app.

### Part 5: Submission

- **Submit Your Assignment**:
  - Provide the URL to your GitHub repository as your assignment submission.

## Rubric

### Node.js Installation and Verification - 5 points

- **Complete (5 pts)**: Demonstrates successful installation and setup of a Next.js project, verified through terminal commands.
- **Partial (3 pts)**: Project setup is mostly correct, but minor issues are present.
- **Limited (0 pts)**: Next.js project is not successfully created or setup issues prevent project execution.

### GitHub Repository Setup - 5 points

- **Complete (5 pts)**: The GitHub repository is correctly set up with all necessary files pushed, including a meaningful `README.md`.
- **Partial (3 pts)**: The repository is created, but some files are missing, or the `README.md` lacks detail.
- **Limited (0 pts)**: Did not create a GitHub repository or did not push the project files.

### Script Execution - 5 points

- **Complete (5 pts)**: The Next.js development server runs successfully with no errors, and all pages are accessible.
- **Partial (3 pts)**: The server runs, but there are minor issues accessing some pages or with page content.
- **Limited (0 pts)**: The development server does not run or pages are not correctly created or accessible.

### Documentation in README.md - 5 points

- **Complete (5 pts)**: The `README.md` thoroughly documents the project setup process, structure, and how to run the project, including a screenshot of the browser.
- **Partial (3 pts)**: The `README.md` includes some documentation but is incomplete or lacks clarity.
- **Limited (0 pts)**: Little to no documentation is provided in the `README.md`.

### Submission Completeness - 5 points

- **Complete (5 pts)**: Provides a link to the fully updated GitHub repository, including a well-documented `README.md`.
- **Partial (3 pts)**: The GitHub link is provided, but the documentation is incomplete or lacks necessary detail.
- **Limited (0 pts)**: Fails to provide a GitHub link, or the repository is incomplete or significantly lacks required elements.
