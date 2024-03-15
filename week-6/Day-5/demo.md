# Hour 1: Integrating Firebase Authentication into the Todo App

<!-- TODO Review these notes and change anything that may not fit.  -->

## Overview

In this session, we'll introduce Firebase Authentication and integrate it into our Todo application. Firebase Authentication provides easy-to-use APIs and ready-made UI libraries to authenticate users to your app. We'll implement a basic email and password sign-in method.

## Step 1: Setup Firebase Authentication

Before integrating Firebase Authentication into our app, ensure that you've set up Firebase in your project and enabled the Email/Password sign-in method in the Firebase Console.

### Code Snippet

```
import { initializeApp } from 'firebase/app';
import { getAuth, createUserWithEmailAndPassword, signInWithEmailAndPassword } from 'firebase/auth';

// Your web app's Firebase configuration (Replace with your actual config object)
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
```

## Step 2: Create User Sign-Up Functionality

We'll create a simple form where new users can sign up by entering their email and password. This form will connect to Firebase to create a new user account.

### Code Snippet for Sign-Up Form

```
import React, { useState } from 'react';

const SignUpForm = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  const handleSubmit = async (e) => {
    e.preventDefault();
    try {
      await createUserWithEmailAndPassword(auth, email, password);
      console.log('User account created & signed in!');
    } catch (error) {
      console.error('Error signing up:', error);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Email:
        <input type="email" value={email} onChange={(e) => setEmail(e.target.value)} />
      </label>
      <label>
        Password:
        <input type="password" value={password} onChange={(e) => setPassword(e.target.value)} />
      </label>
      <button type="submit">Sign Up</button>
    </form>
  );
};

export default SignUpForm;
```

## Step 3: Create User Sign-In Functionality

Next, we'll add functionality for users to sign in using their email and password. This will involve creating another form similar to the sign-up form but will use the `signInWithEmailAndPassword` method.

### Code Snippet for Sign-In Form

```
import React, { useState } from 'react';

const SignInForm = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  const handleSubmit = async (e) => {
    e.preventDefault();
    try {
      await signInWithEmailAndPassword(auth, email, password);
      console.log('User signed in!');
    } catch (error) {
      console.error('Error signing in:', error);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Email:
        <input type="email" value={email} onChange={(e) => setEmail(e.target.value)} />
      </label>
      <label>
        Password:
        <input type="password" value=password onChange={(e) => setPassword(e.target.value)} />
      </label>
      <button type="submit">Sign In</button>
    </form>
  );
};

export default SignInForm;
```

This module will guide the students through setting up Firebase Authentication, creating user accounts, and signing in with email and password. Ensure you have the Firebase project configured and the necessary Firebase services imported in your application.

<!-- ! Hour 2 -->

# Hour 2: Security and Moving to Production

## Overview

In this part of the session, we'll focus on securing our application, particularly looking at Firestore security rules, and then we will cover the steps necessary to move our Todo app to production. Ensuring our application is secure before launch is crucial to protect user data and maintain a trustworthy platform.

## Step 1: Understanding Firestore Security Rules

Firestore Security Rules play a vital role in protecting your data. They allow you to control access to documents and collections in your database based on authentication status, request types, and the content of the documents.

### Basic Rules Overview

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Allow read/write access to all users under any condition
    // Note: This is not recommended for production!
    match /{document=**} {
      allow read, write: if false; // Change to `true` for testing, but ensure to implement more secure rules for production.
    }
  }
}
```

### Secure Rules Example

For a Todo app, you want to ensure that only authenticated users can read and write their own todos. Here's an example of how you might write these rules:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /todos/{todoId} {
      // Allows read/write access only if the user is authenticated and the todo belongs to them
      allow read, write: if request.auth != null && request.auth.uid == resource.data.userId;
    }
  }
}
```

## Step 2: Securing Firebase Authentication

Ensure that your Firebase Authentication setup includes:

- Email verification for new accounts
- Strong password requirements
- Proper handling of authentication states across the app

### Implementing Email Verification (Snippet)

```
// After creating a new user
createUserWithEmailAndPassword(auth, email, password)
  .then((userCredential) => {
    // Send verification email
    userCredential.user.sendEmailVerification();
    console.log('Verification email sent.');
  })
  .catch((error) => {
    console.error('Error sending verification email:', error);
  });
```

## Step 3: Preparing for Production

Before moving your Todo app to production, ensure you have:

- Reviewed and tightened Firestore Security Rules
- Enabled email verification in Firebase Authentication
- Performed thorough testing, including edge cases and user acceptance testing (UAT)
- Set up environment variables for sensitive information (e.g., Firebase config) instead of hard-coding them in your files

### Deploying Your React App

To deploy your React app, you can use services like Firebase Hosting, Netlify, or Vercel. Here's a basic overview of deploying with Firebase Hosting:

1. Install Firebase CLI: `npm install -g firebase-tools`
2. Log in to Firebase: `firebase login`
3. Initialize your project: `firebase init`
4. Build your React app: `npm run build`
5. Deploy to Firebase Hosting: `firebase deploy`

With these steps, your Todo app should be securely configured and ready for production. Remember, security is an ongoing process, and you should regularly review and update your security practices as your app evolves.
