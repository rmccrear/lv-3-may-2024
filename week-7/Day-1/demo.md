# Day 1: Project Planning and Initial Setup

Today marks the beginning of our capstone project development - the Community Market App. This session is designed to guide you through the initial planning and setup phases, ensuring a solid foundation for the application development process.

## Part 1: Introduction and Planning

### Objectives and Core Features

Start by introducing the Community Market App project to your students. Explain the main objectives of the app, such as providing a platform for users to buy and sell goods within a community setting.

### Building Wireframes

Encourage students to draft wireframes for the app's key pages. This could be done using tools like Figma, Sketch, or even pen and paper. Wireframes should include the sign-up/login pages, product listing page, and product details page.

## Part 2: Project Setup

### Setting Up the Next.js Project

Instruct students to open their terminal and run the following commands to create a new Next.js app:

```bash
npx create-next-app@latest community-market-app
cd community-market-app
```

Encourage students to update `README.md` with the project's description, setup instructions, and contributions guidelines.

### Defining User Stories

Together with your students, define user stories that cover all the functionalities you want your app to have. Examples of user stories might include:

- As a user, I want to sign up and log into the app, so that I can access personal and secure space within the app.
- As a seller, I want to list my products, so that buyers can discover them.
- As a buyer, I want to browse listed products, so that I can make purchases.

### Integrating Firebase

Continue in the terminal with the Firebase integration:

```bash
npm install firebase
```

### Setting Up Firebase Configuration

Have students create a `firebaseConfig.js` file within the `utils` directory to store Firebase configuration:

1. Create a `utils` directory and `firebaseConfig.js` file:

```bash
mkdir utils && touch utils/firebaseConfig.js
```

2. In `firebaseConfig.js`, instruct students to paste their Firebase project configuration:

```js
// utils/firebaseConfig.js
import { initializeApp } from 'firebase/app';

const firebaseConfig = {
  // Your Firebase configuration object from firebases website after creating a new app
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);

export default app;
```

### Establishing Project Structure and Coding Standards

Discuss the importance of maintaining a consistent project structure and coding standards. Suggest a project structure such as:

- `src/app/components/`: for React components.
- `src/app/`: for Next.js pages.
- `src/app/styles/`: for CSS modules and global styles.
- `src/app/utils/`: for utility functions and Firebase configuration.

## Creating Initial Components Based on Wireframe Analysis

After analyzing the wireframes, start creating some of the needed components for the application. No styles are needed at this stage, just the major parts like the header, main content area, and any other significant components.

1. **Header Component**:

```js
// src/app/components/Header.js
export default function Header() {
  return (
    <header>
      <h1>Community Market</h1>
      // Placeholder for navigation
      <nav>Navigation Placeholder</nav>
    </header>
  );
}
```

2. **Main Content Area Component**:

```js
// src/app/components/MainContent.js
export default function MainContent() {
  return (
    <main>
      <p>Main content area placeholder</p>
    </main>
  );
}
```

3. **Footer Component** (Optional):

```js
// src/app/components/Footer.js
export default function Footer() {
  return (
    <footer>
      <p>Footer content placeholder</p>
    </footer>
  );
}
```

Instruct students to create these components and integrate them into the main app structure, typically within `src/app/page.js` or other relevant pages.

## Conclusion

By the end of this session, students will have a clear understanding of the project's objectives, a basic wireframe design, a structured Next.js project integrated with Firebase, and a preliminary README.md. This solid foundation sets the stage for the exciting development journey ahead.
