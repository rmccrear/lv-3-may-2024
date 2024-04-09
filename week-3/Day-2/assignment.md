# Assignment: Styles Assignment 2

## Objective

Explore the integration of animations in a Next.js application using Framer Motion. You'll create a simple application that displays three images with engaging animations to demonstrate your understanding of animation effects and their implementation in web development.

## Instructions

### Part 1: Setting Up Your Project

1. **Create a New Next.js App**:

   - Use `create-next-app` to initiate your project. Choose a project name that reflects the nature of this assignment, like `framer-motion-showcase`.

2. **Install Dependencies**:
   - Install Framer Motion by running `npm install framer-motion` in your project directory. This library enables the animation of elements in your React applications.

### Part 2: Building Your Application

1. **Prepare Your Images**:

   - Select three images from Unsplash that you find visually appealing. Download these images and add them to the `public` folder in your Next.js project.

2. **Create Animated Components**:

   - Develop three separate components, each responsible for displaying one of the images you've chosen. Name these components in a way that reflects the content or theme of the images, such as `MountainView.js`, `Cityscape.js`, and `ForestPath.js`.
   - In each component, use a `motion.div` wrapper from Framer Motion to enclose an `<Image>` tag for displaying your selected image. Set up animations for transitions or while hovering. Examples of animations include scaling up on hover, fading in on load, or rotating slightly to catch the viewer's attention.

3. **Integrate Components into Your Main Page**:
   - Import and use your animated components in the `index.js` page. Arrange them in a visually pleasing layout using CSS Grid or Flexbox.

### Part 3: Deploying Your Project

1. **Deploy to Netlify**:
   - Follow Netlify's documentation to deploy your Next.js application. Ensure your GitHub repository is connected to Netlify and configure the build settings as necessary.

## Submission

- **GitHub Repository**: Submit the URL of your GitHub repository. Ensure it's public and contains your final code and a README.md that briefly explains your project and its structure.
- **Live Application**: Provide the Netlify URL where your application is hosted.

## Rubric

### Project Setup and Dependency Management

- **Complete (5 pts)**: Next.js project is correctly initiated with Framer Motion installed. Dependencies are properly managed, and images are added to the `public` folder following best practices.
- **Partial (3 pts)**: The project setup or dependency management shows minor errors. For instance, images may not be optimized or placed correctly. Framer Motion is installed but with minor issues in its application setup.
- **Limited (0 pts)**: Significant issues with project initialization or dependency management. Framer Motion is not installed correctly, or images are missing from the `public` folder.

### Implementation of Animated Components

- **Complete (5 pts)**: Each component is implemented with unique and engaging animations, demonstrating an effective use of Framer Motion for all images.
- **Partial (3 pts)**: Components are implemented with animations, but they lack variety or creativity. There's room for improvement in animation application or component structure.
- **Limited (0 pts)**: Components lack proper animations or are not implemented correctly. There's a significant misunderstanding or misapplication of Framer Motion.

### Creativity and Visual Appeal

- **Complete (5 pts)**: The chosen animations significantly enhance the visual appeal and engagement of the application. Creativity in animation use is evident.
- **Partial (3 pts)**: Animations contribute to the visual appeal, but the creative use of Framer Motion is limited. The application could benefit from more innovative animation ideas.
- **Limited (0 pts)**: The application lacks creativity in animations. Animations are either too basic, improperly implemented, or do not contribute positively to the user experience.

### Code Organization and Cleanliness

- **Complete (5 pts)**: The code is excellently organized and written, following best coding practices. The application structure is logical, and component code is clean and efficient.
- **Partial (3 pts)**: The code is mostly well-organized, but there are areas of improvement. Minor issues with code cleanliness or organization could be addressed for better readability or performance.
- **Limited (0 pts)**: The code is poorly organized or written, not following best practices. Significant issues with code cleanliness or structure, impacting readability and maintainability.

### Deployment and Documentation

- **Complete (5 pts)**: The application is successfully deployed to Netlify, with the repository containing concise, informative documentation of the project setup and deployment process.
- **Partial (3 pts)**: The application is deployed, but documentation is lacking detail or clarity about certain aspects of the project or deployment process.
- **Limited (0 pts)**: The application is not correctly deployed, or documentation is insufficient, failing to describe the project setup and deployment adequately.
