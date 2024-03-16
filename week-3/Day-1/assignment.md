# Assignment: Styles Assignment 1

## Objective

The goal of this assignment is to develop a Next.js application using advanced styling techniques, specifically Sass with the 7-1 architecture, SCSS Modules, and BEM methodology. You will create a user profile page that showcases dynamic styling and user interaction. Additionally, deploying your application to Netlify will be part of this assignment, enabling you to practice deploying Next.js applications.

## Instructions

### Part 1: Setup and Styling

1. **Initialize a New Next.js Project**:

   - Use `create-next-app` to start a new project. Ensure Node.js is installed on your machine.
   - Install Sass in your project by running `npm install sass`.

2. **Implement the 7-1 Sass Architecture**:

   - Organize your Sass files following the 7-1 architecture pattern within a `styles/` directory.
   - Set up a main Sass file (`styles.scss`) to import all Sass partials, and include this file in `_app.js` or `_app.tsx` for global styles.

3. **Apply SCSS Modules with BEM**:
   - For each component (e.g., `Header`, `UserProfile`), create a SCSS module file. Utilize the BEM methodology for class naming within these files.

### Part 2: User Profile Page Development

1. **Create User Profile Component**:

   - Design a `UserProfile` component to display user information such as name, biography, and hobbies, passed as props.

2. **Dynamic Content and Conditional Rendering**:

   - Use conditional rendering to display "No biography available" if the biography prop is empty.
   - Render hobbies dynamically with the `map` function, showing "No hobbies listed" when the list is empty.

3. **Implement Client-Side Navigation**:
   - Set up client-side navigation using the Next.js `Link` component for navigating between the Home page and the User Profile page.

### Part 3: Deploying Your Application to Netlify

1. **Prepare Your Application for Deployment**:

   - Ensure your application builds successfully by running `npm run build`.

2. **Deploy to Netlify**:
   - Follow Netlify’s documentation to deploy your Next.js application. This involves connecting your GitHub repository to Netlify and configuring it for deployment.

### Part 4: Documentation and Reflection

- **Document Your Process**:
  - Update the README.md file to document the steps taken during the assignment, focusing on styling and deployment.
- **Include Deployment URL**:
  - Add the URL of your deployed application on Netlify to the README.md.

## Submission

Submit the URL of your GitHub repository containing the completed project and the updated README.md. Ensure your repository is public. Also, submit the URL of your deployed application on Netlify.

## Rubric

### Node.js Installation and Verification - 5 points

- **Complete (5 pts)**: Node.js and npm are correctly installed, and the project is initialized without errors.
- **Partial (3 pts)**: Minor issues with installation or project initialization that do not significantly impact project setup.
- **Limited (0 pts)**: Node.js and npm are not correctly installed, or project cannot be initialized due to errors.

### Implementation of 7-1 Sass Architecture - 5 points

- **Complete (5 pts)**: Successfully implements the 7-1 Sass architecture with clear organization of styles according to the pattern.
- **Partial (3 pts)**: Implements most of the 7-1 architecture pattern, but some styles or files may be misplaced or missing.
- **Limited (0 pts)**: Does not implement the 7-1 architecture pattern or significantly deviates from the structure.

### SCSS Modules and BEM Naming - 5 points

- **Complete (5 pts)**: Effectively uses SCSS Modules and the BEM naming convention across all components, demonstrating a clear understanding of scoped styling and organization.
- **Partial (3 pts)**: Uses SCSS Modules and BEM naming with minor inconsistencies or errors.
- **Limited (0 pts)**: Does not use SCSS Modules or BEM naming correctly, leading to global style conflicts or poor organization.

### Deployment to Netlify - 5 points

- **Complete (5 pts)**: The application is successfully deployed to Netlify with no issues. The deployed site is functional and accessible.
- **Partial (3 pts)**: The application is deployed to Netlify, but minor issues affect the site's functionality or accessibility.
- **Limited (0 pts)**: Fails to deploy the application to Netlify, or the deployed site is not functional.

### Documentation in README.md - 5 points

- **Complete (5 pts)**: README.md clearly documents the development process, styling strategy, deployment steps, and includes the Netlify deployment URL.
- **Partial (3 pts)**: README.md documents most of the process but lacks details in certain areas or omits the deployment URL.
- **Limited (0 pts)**: Documentation is inadequate, missing critical information or does not include the deployment URL.
