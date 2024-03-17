# Assignment: Styles Assignment 2

## Objective

Dive into the world of animations with Framer Motion by integrating it into a Next.js project. For this assignment, you're tasked with creating an engaging, interactive photo gallery. This gallery will not only display images but also feature dynamic animations for photo transitions and interactions, such as hovering over or selecting an image. Furthermore, you'll deploy your finished project to Netlify, showcasing your ability to bring projects to life on the web.

## Instructions

### Part 1: Setup Your Next.js Project

1. **Initialize Your Project**:

   - Generate a new Next.js application using `create-next-app`. This serves as the foundation for your interactive photo gallery.
   - Ensure Node.js is correctly installed on your machine to proceed with the project setup.

2. **Install Framer Motion**:
   - Add Framer Motion to your project dependencies by running `npm install framer-motion` in your project's root directory. This command equips your project with the animation library needed to bring your photo gallery to life.

### Part 2: Develop an Interactive Photo Gallery

1. **Construct a `PhotoGallery` Component**:

   - Create a `PhotoGallery` component within your project. This component should display images in a visually appealing grid layout. Consider using CSS Grid or Flexbox for this layout.
   - Wrap each image in a `motion.div` from Framer Motion to prepare for animation implementation.

2. **Implement Dynamic Animations**:

   - Apply hover animations to each photo to indicate interactivity, such as subtle scale increases or brightness adjustments. This enhances user engagement and visual feedback.
   - Introduce transition effects between photos to smooth out the viewing experience. Explore different animation types offered by Framer Motion, such as fades, slides, or scales.

3. **Modal View for Selected Images**:
   - Implement a modal that activates when an image is clicked, displaying the image in a larger format. Animate the modal's entrance and exit for a polished user experience.
   - This modal should also be dismissible, with an animation reversing the entrance effect.

### Part 3: Deployment to Netlify

1. **Prepare for Production**:
   - Build your project for production by executing `npm run build`. This step compiles your application, optimizing it for deployment.
2. **Deploy to Netlify**:
   - Utilize Netlify's services to deploy your Next.js application. You'll need to connect your GitHub repository to Netlify and configure the build settings based on your project's requirements.

### Part 4: Comprehensive Documentation

- **Detailed README.md**:
  - Provide a thorough documentation of your project in the README.md file. Include an overview of your project, a step-by-step guide on how you implemented Framer Motion animations, and any obstacles you encountered along with their solutions.
- **Deployment Information**:
  - Ensure the README.md contains the Netlify URL where your project is hosted, allowing others to view and interact with your photo gallery.

## Submission

- **GitHub Repository**: Share the URL of your GitHub repository, making sure it's set to public access and includes your final code and a detailed README.md.
- **Live Application**: Also submit the URL of your application deployed on Netlify.

## Rubric

### Project Initialization and Framer Motion Integration - 5 points

- **Complete (5 pts)**: Next.js project is flawlessly set up with Framer Motion integrated. Initial setup adheres to best practices.
- **Partial (3 pts)**: Minor issues with the initial setup or integration of Framer Motion. The project is mostly set up correctly, but there are small areas for improvement.
- **Limited (0 pts)**: Significant problems with setting up the project or integrating Framer Motion. Key steps are missed or done incorrectly.

### Interactive Photo Gallery Implementation - 5 points

- **Complete (5 pts)**: `PhotoGallery` component is excellently implemented with a grid layout and each image is properly wrapped for animations. The gallery is interactive and user-friendly.
- **Partial (3 pts)**: The photo gallery is implemented with most requirements met. However, the layout or interactivity has minor flaws.
- **Limited (0 pts)**: The photo gallery lacks proper implementation, missing significant features or interactivity elements.

### Creativity and Effectiveness of Animations - 5 points

- **Complete (5 pts)**: Animations are creatively applied and effectively enhance the user experience. Hover and transition animations are particularly well-executed.
- **Partial (3 pts)**: Animations are present but could be more creative or effective. Some animations do not contribute significantly to the user experience.
- **Limited (0 pts)**: Animations are poorly implemented, lacking creativity or negatively impacting the user experience.

### Modal Functionality and Animation - 5 points

- **Complete (5 pts)**: Modal for viewing selected images is flawlessly implemented with smooth and engaging entrance and exit animations.
- **Partial (3 pts)**: The modal is functional but the animations are not fully polished or exhibit minor issues.
- **Limited (0 pts)**: Significant issues with the modal's functionality or animations. The modal may not work as expected or animations are missing.

### Deployment to Netlify and Documentation - 5 points

- **Complete (5 pts)**: The application is successfully deployed to Netlify with a comprehensive README.md documenting the project and deployment process. The live URL is included.
- **Partial (3 pts)**: The application is deployed, but the README.md lacks some detail about the project or deployment process. The live URL may be missing important information.
- **Limited (0 pts)**: Fails to deploy the application correctly, or the README.md does not adequately document the project. The live URL is not provided or is incorrect.
