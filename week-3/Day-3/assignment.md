# Assignment: Styles Assignment 3

## Objective

Combine React Bootstrap's component-based design with the utility-first CSS approach of Tailwind CSS to create a modern, responsive landing page. This assignment challenges you to leverage both frameworks within a Next.js project to construct a page that not only looks great but also scales well across devices. Additionally, deploy your finished product to Netlify to share your work with the world.

## Instructions

### Part 1: Project Setup

1. **Initialize a Next.js Application**:

   - Use `create-next-app` to kickstart your project. Ensure Node.js is up-to-date on your system.

2. **Install Dependencies**:

   - Run `npm install react-bootstrap bootstrap` to add React Bootstrap to your project.

3. **Global Styles Configuration**:
   - Import Bootstrap's CSS in your `src/app/layout.js` file to ensure global availability.
   - Set up Tailwind by creating its config files and importing the base styles as recommended in the Tailwind CSS documentation.

### Part 2: Build the Landing Page

1. **Navbar Implementation**:

   - Utilize React Bootstrap to add a `Navbar` component. Include links to different sections of your landing page that will be developed.

2. **Hero Section**:

   - Design a compelling Hero section using Tailwind CSS for styling. This section should include a headline, a brief description, and a call-to-action (CTA) button.

3. **Features Section**:

   - Create a grid or card layout using React Bootstrap to showcase the main features of your project or service. Customize the appearance with Tailwind CSS.

4. **Footer**:
   - Implement a Footer component with React Bootstrap. Include social links, contact information, or any relevant links.

### Part 3: Responsiveness and Interactivity

1. **Responsive Design**:

   - Ensure your landing page is responsive and looks great on all device sizes. Use Tailwind's responsive utilities to adjust layouts and font sizes.

2. **Add Interactivity**:
   - Enhance user experience by adding interactive elements such as hover effects on buttons or cards. Experiment with Tailwind's state variants (e.g., `hover:`).

### Part 4: Deployment

1. **Netlify Deployment**:
   - Prepare your project for deployment by running `npm run build`.
   - Deploy your Next.js application to Netlify. Link your project's GitHub repository to Netlify and follow the steps to deploy.

### Part 5: Documentation

- **README.md Update**:
  - Clearly document the purpose of your project, the steps you took to implement the features, and any challenges you faced.
- **Include Deployment URL**:
  - Provide the Netlify URL of your deployed landing page in the README.md.

## Submission

- **GitHub Repository Link**: Ensure your repository is public and contains the final version of your code and an updated README.md.
- **Deployed Application URL**: Share the link to your project hosted on Netlify.

## Rubric

### Project Setup and Integration - 5 points

- **Complete (5 pts)**: Perfect setup of Next.js, React Bootstrap, and Tailwind CSS. All configurations are correctly implemented for optimal use.
- **Partial (3 pts)**: Most configurations are correctly implemented, with minor issues that do not significantly impact functionality.
- **Limited (0 pts)**: Significant configuration errors that adversely affect the project's functionality.

### Landing Page Design and Functionality - 5 points

- **Complete (5 pts)**: The landing page is aesthetically pleasing with a clear, functional layout, effectively using both React Bootstrap and Tailwind CSS.
- **Partial (3 pts)**: The design is generally good, with minor issues in layout or styling choices. Adequate use of React Bootstrap and Tailwind CSS.
- **Limited (0 pts)**: Poor design with major issues. Ineffective use of styling frameworks.

### Responsiveness and Interactivity - 5 points

- **Complete (5 pts)**: The page is fully responsive and interactive, providing an excellent user experience across all devices.
- **Partial (3 pts)**: Generally responsive with some interactive elements. Minor issues in responsiveness or interactivity.
- **Limited (0 pts)**: Lack of responsiveness and minimal interactivity, leading to a poor user experience.

### Deployment and Documentation - 5 points

- **Complete (5 pts)**: Successfully deployed to Netlify with comprehensive documentation in README.md. Deployment URL is included.
- **Partial (3 pts)**: Deployment completed with basic documentation. Some details may be missing or unclear. Deployment URL is included.
- **Limited (0 pts)**: Issues with deployment. Incomplete or unclear documentation without a deployment URL.

### Creativity and Use of Features - 5 points

- **Complete (5 pts)**: High creativity in design and feature use. Excellent integration of React Bootstrap and Tailwind CSS features that enhance the site's appeal.
- **Partial (3 pts)**: Good creativity with functional use of features. Some innovative uses of React Bootstrap and Tailwind CSS.
- **Limited (0 pts)**: Minimal creativity or innovation in feature use. Poor integration of the frameworks' capabilities.
