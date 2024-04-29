## Week 6, Day 1, Hour 1: Introduction to Firebase and Its Services

Today, we embark on an exciting journey to integrate Firebase into Next.js applications. Firebase offers a comprehensive suite of tools that make it easier to develop high-quality apps, enhance user engagement, and grow your user base. Let's start by setting up Firebase in a Next.js project.

### Step 1: Understanding Firebase

- **Discuss Firebase's capabilities**: Firebase provides a variety of services such as authentication, real-time database, cloud functions, hosting, and more. It's a platform developed by Google for creating mobile and web applications.

- **Open the Firebase documentation**: Navigate to [Firebase Documentation](https://firebase.google.com/docs). Spend a few minutes exploring the overview section to understand the breadth of features Firebase offers. Highlight how Firebase's scalability and integration capabilities make it a great choice for modern web applications.

### Step 2: Creating a Firebase Project

1. **Visit the Firebase Console**: Open [Firebase Console](https://console.firebase.google.com/) and sign in with your Google account. Discuss the importance of creating a project in Firebase console as it serves as the container for your app's data, authentication, and configuration settings.

2. **Create a new project**: Click on "Add project" and follow the prompts. Explain each step in the project creation process, highlighting the option to enable Google Analytics for your project.

### Step 3: Installing Firebase SDK

1. **Initialize a Next.js project**: If you haven't already, create a new Next.js application by running:

   ```bash
   npx create-next-app@latest
   ```

2. **Install Firebase**: Navigate to your project directory and install the Firebase package:

   ```bash
   npm install firebase
   ```

When discussing the role of the Firebase SDK, you might say:

The Firebase SDK, which stands for Software Development Kit, acts as a crucial bridge between our Next.js application and the various Firebase services we intend to use. Similar to how we configured Webpack and Babel last week to tailor our development environment, the Firebase SDK customizes our interaction with Firebase's suite of tools. By integrating this SDK, we gain streamlined access to services like Authentication, Firestore Database, Cloud Functions, and more. The SDK simplifies the complexity of communicating with Firebase's backend, providing a friendly API for our use. It enables key functionalities in our application, such as user authentication and real-time data operations, supporting rapid development and scalability through Firebase's cloud infrastructure.

Think of it like an "on-switch" for features.

### Step 4: Initializing Firebase in Your Next.js Project

1. **Create a Firebase configuration file**: In your Next.js project, create a new file `firebaseConfig.js` in the `src` folder. Explain the significance of storing your Firebase project's configuration in this file.

2. **Add Firebase configuration**: Go back to the Firebase Console, navigate to your project settings, and find your project's configuration. Copy the configuration object and paste it into `firebaseConfig.js`:

https://firebase.google.com/docs/web/setup#initialize_the_sdk

```js
// Import the functions you need from the SDKs you need
import { initializeApp } from 'firebase/app';
import { getAuth, GoogleAuthProvider } from 'firebase/auth';

const provider = new GoogleAuthProvider();
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: 'AIzaSyC6EvK2AaZmTVH5IUgIdgY1bS-example',
  authDomain: 'example-stand-f0343.firebaseapp.com',
  projectId: 'example-stand-f0343',
  storageBucket: 'example-stand-f0343.appspot.com',
  messagingSenderId: '476457416155',
  appId: '1:476457416155:web:216dea7a1e39f6e17fe3fe',
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
export { auth, provider };
```

### Conclusion

- **Review**: Recap what we've done so far—creating a Firebase project, installing Firebase SDK, and initializing Firebase in a Next.js application.
- **Open the Firebase documentation again**: This time, navigate to the "Get Started" section specific to the Web (https://firebase.google.com/docs/web/setup). Discuss the importance of referring to the documentation for further customization and feature integration.

This hour has set the foundation for integrating Firebase into Next.js applications. In the next session, we'll dive into Firebase Authentication and how to implement a basic

<!-- ! Hour 2 -->

## Day 1, Hour 2: Introduction to Firebase Authentication

In this hour, we're diving into Firebase Authentication. We'll learn how to set up various authentication methods, with a focus on Google Sign-In, and how to implement a basic authentication flow in a Next.js project.

### Step 1: Set Up Firebase Authentication

Firebase Authentication provides a lot of options out of the box, including email/password, OAuth providers (Google, Facebook, Twitter, etc.), and phone authentication.

This code snippet demonstrates how to create a GoogleAuthProvider instance and use it to sign in with a popup. You can handle the signed-in user's information or errors accordingly.

2. **Implement the Sign-In Button**:
   In your component or page where you want to display the sign-in button, import and use the `signInWithGoogle` function.

```jsx
'use client';
import { signInWithPopup } from 'firebase/auth';
import React from 'react';
import { auth, provider } from '../../firebaseConfig';

export default function GoogleSignIn() {
  const handleGoogleSignIn = async () => {
    try {
      const result = await signInWithPopup(auth, provider);
      const user = result.user;
      console.log('User signed in:', user.displayName);
    } catch (error) {
      console.error('Error signing in:', error);
    }
  };

  return <button onClick={handleGoogleSignIn}>Sign in with Google</button>;
}
```

#### Add in state management and conditional rendering:

```jsx
'use client';
import { signInWithPopup } from 'firebase/auth';
import React, { useState } from 'react';
import { auth, provider } from '../../firebaseConfig';

export default function GoogleSignIn() {
  const [user, setUser] = useState(null);
  const handleGoogleSignIn = async () => {
    try {
      const result = await signInWithPopup(auth, provider);
      const user = result.user;
      console.log('User signed in:', user.displayName);
      setUser(user);
    } catch (error) {
      setUser(null);
      console.error('Error signing in:', error);
    }
  };

  return (
    <>
      <button onClick={handleGoogleSignIn}>Sign in with Google</button>
      {user && <p>Welcome back, {user.displayName}</p>}
      {!user && <p>Click the button above to sign in!</p>}
    </>
  );
}
```

### Step 3: Handling User Sessions

Firebase Authentication integrates with Next.js to manage user sessions. Let's briefly discuss how to detect and react to authentication state changes, such as logging in and out.

```jsx
'use client';
import { onAuthStateChanged, signInWithPopup, signOut } from 'firebase/auth';
import React, { useEffect, useState } from 'react';

import { auth, provider } from '../../firebaseConfig';

export default function GoogleSignIn() {
  const [userObject, setUser] = useState(null);

  useEffect(() => {
    const unsubscribe = onAuthStateChanged(auth, (user) => {
      if (user) {
        setUser(user); // Set the user object when authenticated
      } else {
        setUser(null); // Clear the user object when not authenticated
      }
    });

    return () => unsubscribe(); // Cleanup subscription on component unmount
  }, []);

  const handleGoogleSignIn = async () => {
    try {
      const result = await signInWithPopup(auth, provider);
      setUser(result.user); // Store user object after successful sign-in
      console.log('User signed in:', result.user.displayName);
    } catch (error) {
      setUser(null); // Clear state on sign-in error
      console.error('Error signing in:', error);
    }
  };

  const handleLogout = async () => {
    try {
      await signOut(auth); // Logout using Firebase
      setUser(null); // Clear the user state after logout
      console.log('User logged out');
    } catch (error) {
      console.error('Error during logout:', error);
    }
  };

  return (
    <>
      {!userObject ? (
        <button onClick={handleGoogleSignIn}>Sign in with Google</button>
      ) : (
        <>
          <p>Welcome back, {userObject.displayName}!</p>
          <button onClick={handleLogout}>Logout</button>
        </>
      )}
    </>
  );
}
```

### Conclusion

By integrating Firebase Authentication with Google Sign-In, we've laid the foundation for securing our Next.js application. Firebase offers flexibility to support various authentication providers, enabling us to cater to a wide array of user preferences.

Remember to refer to the [Firebase Authentication Documentation](https://firebase.google.com/docs/auth) for detailed information on configuring other authentication methods and further customizing the authentication flow.
