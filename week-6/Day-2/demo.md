## Day 2, Hour 1: Simplifying Firebase Authentication in Next.js

In this session, we simplify our Firebase Authentication integration by using `useState` and `useEffect`. This approach manages authentication state without introducing complex patterns, making it easier for beginners to understand Firebase Authentication in Next.js.

### Step 1: Initialize Firebase in Your Next.js Project

Ensure you've set up Firebase in your Next.js project. Refer to previous instructions if needed for installing Firebase and configuring your Firebase project.

### Step 2: Implement Google Sign-In Functionality

1. **Create a Firebase Configuration File**:
   Set up Firebase configuration in a `firebaseConfig.js` file, initializing Firebase and exporting it for use in your application.

   ```jsx
   // firebaseConfig.js
   import { initializeApp } from 'firebase/app';
   import { getAuth, GoogleAuthProvider } from 'firebase/auth';

   const firebaseConfig = {
     apiKey: 'your-api-key',
     authDomain: 'your-auth-domain',
     projectId: 'your-project-id',
     storageBucket: 'your-storage-bucket',
     messagingSenderId: 'your-messaging-sender-id',
     appId: 'your-app-id',
   };

   const app = initializeApp(firebaseConfig);
   export const auth = getAuth(app);
   export const googleProvider = new GoogleAuthProvider();
   ```

2. **Implement Google Sign-In Component**:
   Create a component that allows users to sign in with Google and logs out. Use `useState` to manage user state and `useEffect` to listen for authentication changes.

   ```jsx
   import React, { useState, useEffect } from 'react';
   import { onAuthStateChanged, signInWithPopup, signOut } from 'firebase/auth';
   import { auth, googleProvider } from '../lib/firebaseConfig'; // Adjust path as needed
   import { useRouter } from 'next/navigation';   // For redirecting after logout

   const GoogleSignIn = () => {
     const [user, setUser] = useState(null);
     const router = useRouter(); // Redirect to login after logout

     useEffect(() => {
       const unsubscribe = onAuthStateChanged(auth, (user) => {
         if (user) {
           setUser(user);
         } else {
           setUser(null);
           router.push('/signin'); // Redirect if user is not signed in
         }
       });

       return () => unsubscribe(); // Cleanup subscription on component unmount
     }, []);

     const handleGoogleSignIn = async () => {
       try {
         const result = await signInWithPopup(auth, googleProvider);
         setUser(result.user); // Store user after sign-in
         console.log('User signed in:', result.user.displayName);
       } catch (error) {
         console.error('Error signing in:', error);
         setUser(null); // Clear state if error occurs
       }
     };

     const handleLogout = async () => {
       try {
         await signOut(auth);
         setUser(null); // Reset state after logout
         router.push('/signin'); // Redirect to sign-in page
       } catch (error) {
         console.error('Error during logout:', error);
       }
     };

     return (
       <>
         {!user ? (
           <button onClick={handleGoogleSignIn}>Sign in with Google</button>
         ) : (
           <>
             <p>Welcome back, {user.displayName}!</p>
             <button onClick={handleLogout}>Logout</button>
           </>
         )}
       </>
     );
   };

   export default GoogleSignIn;
   ```

3. **Use the Google Sign-In Component in Your Application**:
   Import and use your `GoogleSignIn` component in any page where you want to enable user authentication.

   ```jsx
   // app/page.js or another page
   import GoogleSignIn from '../components/GoogleSignIn'; // Adjust path

   const HomePage = () => {
     return (
       <main>
         <h1>Welcome to Our Application</h1>
         <GoogleSignIn />
       </main>
     );
   };

   export default HomePage;
   ```

### Step 3: Implement Email/Password Authentication

1. **Enable Email/Password Sign-In Method**:
   Go to the Firebase Console, navigate to the Authentication section, and under the Sign-in method tab, enable the Email/Password provider.

2. **Create Email/Password Sign-In Component**:
   Build a component that allows users to sign in using their email and password. Include a basic form to accept these details.

```jsx
'use client';
import React, { useState } from 'react';
import { createUserWithEmailAndPassword } from 'firebase/auth';
import { auth } from '../../firebaseConfig'; // Adjust path as needed

const EmailPasswordSignUp = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [error, setError] = useState(null);

  const handleSignUp = async (e) => {
    e.preventDefault();
    setError(null); // Reset error state

    try {
      const userCredential = await createUserWithEmailAndPassword(
        auth,
        email,
        password,
      );
      console.log('User registered:', userCredential.user);

      // Additional post-sign-up logic could go here
    } catch (error) {
      console.error('Error signing up:', error);
      setError(error.message); // Store the error message to display
    }
  };

  return (
    <form
      className="m-5"
      onSubmit={handleSignUp}
    >
      <input
        className="m-5 text-black"
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
      />
      <input
        className="m-5 text-black"
        type="password"
        value={password}
        onChange={(e) => setPassword(e.target.value)}
        placeholder="Password"
      />
      <button type="submit">Sign Up</button>
      {error && <p className="text-red-600">{error}</p>} {/* Display error if any */}
    </form>
  );
};

export default EmailPasswordSignUp;
```

```jsx
import React, { useState } from 'react';
import { signInWithEmailAndPassword } from 'firebase/auth';
import { auth } from '../lib/firebaseConfig'; // Adjust path as needed

const EmailPasswordSignIn = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  const handleSignIn = async (e) => {
    e.preventDefault();
    try {
      const userCredential = await signInWithEmailAndPassword(auth, email, password);
      console.log('Signed in:', userCredential.user);
    } catch (error) {
      console.error('Error signing in:', error);
    }
  };

  return (
    <form onSubmit={handleSignIn}>
      <input
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
      />
      <input
        type="password"
        value(password)
        onChange={(e) => setPassword(e.target.value)}
        placeholder="Password"
      />
      <button type="submit">Sign In</button>
    </form>
  );
};

export default EmailPasswordSignIn;
```

3. **Integrate User Session Management**:
   Modify your application to include user session management, allowing users to sign out and restricting access to certain parts of your application based on their authentication status.

### Step 4: Implement Conditional Rendering for Protected Routes

1. **Conditional Rendering Based on Authentication State**:
   Modify your component to display protected content only if the user is authenticated. Otherwise, render a message or redirect to a sign-in page.

```jsx
'use client';
import React, { useState, useEffect } from 'react';
import { useRouter } from 'next/navigation';
import { auth } from '../../../firebaseConfig';
// Adjust path

const ProtectedPage = () => {
  const [user, setUser] = useState(null);
  const router = useRouter();

  useEffect(() => {
    const unsubscribe = auth.onAuthStateChanged((user) => {
      if (!user) {
        router.push('/'); // Redirect if user not authenticated
      } else {
        setUser(user);
      }
    });

    return () => unsubscribe(); // Cleanup on component unmount
  }, [router]);

  if (!user) {
    return <div>Loading or not authorized...</div>; // Render during auth check
  }

  return <div>Welcome, {user.displayName}! This is protected content.</div>;
};

export default ProtectedPage;
```
