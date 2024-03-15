## Day 2, Hour 1: Simplifying Firebase Authentication in Next.js

In this session, we simplify our Firebase Authentication integration by using `useState` and passing props as needed. This method avoids introducing `useContext` too early, making it easier for beginners to understand state management in Next.js with Firebase.

### Step 1: Initialize Firebase in Your Next.js Project

Ensure you've followed the initial steps to set up Firebase in your Next.js project. If not, refer back to the previous instructions to install Firebase and configure your Firebase project.

### Step 2: Implement Google Sign-In Functionality

1. **Create a Firebase Configuration File**: If you haven't already, set up your Firebase configuration in a `firebaseConfig.js` file. This file initializes Firebase and exports it for use in your application.

   ```js
   // firebaseConfig.js
   import firebase from 'firebase/app';
   import 'firebase/auth';

   const firebaseConfig = {
     // Your Firebase project configuration
   };

   if (!firebase.apps.length) {
     firebase.initializeApp(firebaseConfig);
   }

   export const auth = firebase.auth();
   export default firebase;
   ```

2. **Implement the Sign-In Function**: Create a simple sign-in function using the Firebase auth module. You can place this function in the same `firebaseConfig.js` file or a dedicated `auth.js` file within a utilities directory.

   ```js
   // In firebaseConfig.js or auth.js
   import { auth } from './firebaseConfig';

   export const signInWithGoogle = () => {
     const provider = new firebase.auth.GoogleAuthProvider();
     auth.signInWithPopup(provider);
   };
   ```

### Step 3: Create a Sign-In Component

1. **Build a Sign-In Button Component**: Create a component that includes a button for signing in. This component will also display the user's name after successful authentication.

   ```js
   import React, { useState, useEffect } from 'react';
   import { signInWithGoogle, auth } from '../lib/firebaseConfig';

   const SignInButton = () => {
     const [user, setUser] = useState(null);

     useEffect(() => {
       auth.onAuthStateChanged((user) => {
         if (user) {
           setUser({
             displayName: user.displayName,
             email: user.email,
           });
         } else {
           setUser(null);
         }
       });
     }, []);

     return (
       <div>
         {user ? (
           <p>Welcome, {user.displayName}</p>
         ) : (
           <button onClick={signInWithGoogle}>Sign in with Google</button>
         )}
       </div>
     );
   };

   export default SignInButton;
   ```

2. **Use the Sign-In Component in Your Application**: Import and use your `SignInButton` component in any page where you want to enable user authentication.

   ```js
   // pages/index.js or any other page
   import SignInButton from '../components/SignInButton';

   const HomePage = () => {
     return (
       <main>
         <h1>Welcome to Our Application</h1>
         <SignInButton />
       </main>
     );
   };

   export default HomePage;
   ```

### Recap and Documentation Reference

- We've simplified the integration of Firebase Authentication by using `useState` and effects. This approach allows us to manage authentication state without introducing more complex React patterns.
- For further exploration and to understand all available authentication methods, refer to the [Firebase Authentication Documentation](https://firebase.google.com/docs/auth).

By following these steps, you have integrated Firebase Authentication into your Next.js application, enabling users to sign in with Google and displaying their names upon successful authentication.

After setting up Google Sign-In, let's add the ability for users to sign in using their email and password. This method provides a more traditional way of authentication and allows users without Google accounts to access your application.

### Step 1: Enable Email/Password Authentication

1. **Enable Email/Password Sign-In Method**: Go to the Firebase Console, navigate to the Authentication section, and under the Sign-in method tab, enable the Email/Password provider.

### Step 2: Implement Email/Password Sign-In

1. **Create Sign-In Form Component**:
   Let's build a simple form component where users can input their email and password to sign in or register.

   ```js
   import React, { useState } from 'react';
   import { auth } from '../lib/firebaseConfig';

   const EmailPasswordAuth = () => {
     const [email, setEmail] = useState('');
     const [password, setPassword] = useState('');

     const signIn = (e) => {
       e.preventDefault();
       auth
         .signInWithEmailAndPassword(email, password)
         .then((userCredential) => {
           // Signed in
           var user = userCredential.user;
           console.log('Signed in with email and password:', user);
         })
         .catch((error) => {
           console.error('Error signing in with email and password:', error);
         });
     };

     return (
       <form onSubmit={signIn}>
         <input
           type="email"
           value={email}
           onChange={(e) => setEmail(e.target.value)}
           placeholder="Email"
         />
         <input
           type="password"
           value={password}
           onChange={(e) => setPassword(e.target.value)}
           placeholder="Password"
         />
         <button type="submit">Sign In</button>
       </form>
     );
   };

   export default EmailPasswordAuth;
   ```

2. **Handling User Registration**:
   Implement a function to handle new user registration. This function can be part of your `EmailPasswordAuth` component or a separate module.

   ```js
   const register = (e) => {
     e.preventDefault();
     auth
       .createUserWithEmailAndPassword(email, password)
       .then((userCredential) => {
         // Registered
         var user = userCredential.user;
         console.log('User registered:', user);
       })
       .catch((error) => {
         console.error('Error registering:', error);
       });
   };
   ```

### Step 3: Manage User Sessions

Expand on managing user sessions by storing user information in the state and displaying user-specific content after login.

1. **Integrate User Session Management**:
   Modify your application to include user session management, allowing users to sign out and restricting access to certain parts of your application based on their authentication status.

### Conclusion

By integrating email and password authentication alongside Google Sign-In, we've enhanced the flexibility of our authentication system in Next.js. Remember, managing user sessions and data securely is crucial in real-world applications, so always consider security best practices when handling user information.

Refer to the [Firebase Authentication Documentation](https://firebase.google.com/docs/auth) for more details on managing users, securing sessions, and implementing other authentication methods.

<!--! Hour 2  -->

## Day 2, Hour 2: Simplifying Protected Routes with Conditional Rendering

In this hour, we'll explore a straightforward method to implement protected routes in Next.js applications. Instead of using a Higher Order Component, we'll use Firebase's authentication state and conditional rendering to manage access to protected pages.

### Step 1: Set Up State for User Authentication

First, ensure your Firebase setup is complete and the Firebase SDK is initialized in your project. Then, in each page component where you want to implement protected content, we'll use React's `useState` and `useEffect` hooks to listen for changes in the user's authentication status.

1. **Implement State and Effect Hook for Authentication**:
   In your page component, add state for the user and use an effect to update this state based on Firebase's authentication state.

   ```js
   import React, { useState, useEffect } from 'react';
   import { auth } from '../lib/firebaseConfig'; // Adjust the path as necessary

   const ProtectedPage = () => {
     const [user, setUser] = useState(null);

     useEffect(() => {
       const unsubscribe = auth.onAuthStateChanged((user) => {
         if (user) {
           // User is signed in
           setUser(user);
         } else {
           // User is signed out
           setUser(null);
         }
       });

       // Cleanup subscription on unmount
       return () => unsubscribe();
     }, []);

     // Page content goes here
   };
   ```

### Step 2: Use Conditional Rendering to Protect Your Route

Now that we have the user's authentication state, we can conditionally render the page's content or redirect the user to a sign-in page if they are not authenticated.

1. **Conditional Rendering Based on Authentication State**:
   Modify your component to display the protected content only if the user is authenticated. Otherwise, render a message or redirect to a sign-in page.

   ```js
   import React from 'react';
   import { useRouter } from 'next/router';

   const ProtectedPage = () => {
     const [user, setUser] = useState(null);
     const router = useRouter();

     useEffect(() => {
       auth.onAuthStateChanged((user) => {
         if (!user) {
           // If the user is not signed in, redirect to sign-in page
           router.push('/signin');
         } else {
           setUser(user);
         }
       });
     }, [router]);

     if (!user) {
       // Optionally, display a loading indicator or a message while checking auth state
       return <div>Loading or not authorized...</div>;
     }

     return (
       <div>Welcome, {user.displayName}! This is a protected content.</div>
     );
   };

   export default ProtectedPage;
   ```

### Conclusion

By utilizing conditional rendering based on the user's authentication state, you've implemented a basic form of protected routes in your Next.js application. This approach offers a simpler alternative to using Higher Order Components (HOCs) for beginners, keeping your application secure while managing user access effectively.

Remember, as your application grows in complexity, you might consider exploring more advanced patterns for handling authentication and protected routes.
