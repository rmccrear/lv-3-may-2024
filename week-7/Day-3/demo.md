# Day 3: Integrating Firestore Database Operations

Day 3 is dedicated to integrating Firestore database operations into our Community Market App. We will focus on implementing functionality to add new items to the Firestore database and retrieving items to display on the classifieds page.

## Part 1: Setting Up Firestore

Ensure that Firestore is enabled in your Firebase console and that you have initialized Firebase in your project. You should already have the Firebase SDK installed and configured from the previous day.

### Firestore Security Rules

Before we start, make sure your Firestore database has appropriate security rules for read/write operations. For development purposes, you can use the following rules, but be sure to secure your database before going to production.

```bash
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

## Part 2: Adding New Items to Firestore

### Creating AddItem Function

Create a function within your `AddItemModal` component to handle adding new item data to Firestore. This function should be called when the form is submitted.

```javascript
import { db } from './firebaseConfig'; // Import your Firebase config file
import { collection, addDoc } from 'firebase/firestore';

const auth = getAuth();
const userId = auth.currentUser ? auth.currentUser.uid : null;
const handleSubmit = async (e) => {
  e.preventDefault();
  // Prevent submission if there's no logged in user
  if (!userId) {
    console.error('No user logged in');
    return;
  }
  try {
    const docRef = await addDoc(collection(db, 'items'), {
      title,
      description,
      price,
      category,
      condition,
      userId,
    });
    console.log('Document written with ID:', docRef.id);
    handleClose();
  } catch (error) {
    console.error('Error adding document:', error);
  }
};
```

## Part 3: Fetching Items from Firestore

### Creating a Component to Display Items

You should have an `ItemCard` and `Classifieds` component from Day 2. Now, modify the `Classifieds` component to fetch items from Firestore instead of using static data.

```javascript
import React, { useState, useEffect } from 'react';
import { db } from './firebaseConfig'; // Adjust the import path as necessary
import { collection, getDocs } from 'firebase/firestore';
import ItemCard from './ItemCard'; // Adjust the import path as necessary

const Classifieds = () => {
  const [items, setItems] = useState([]);

  useEffect(() => {
    const fetchItems = async () => {
      const querySnapshot = await getDocs(collection(db, 'items'));
      const itemsArray = [];
      querySnapshot.forEach((doc) => {
        itemsArray.push({ id: doc.id, ...doc.data() });
      });
      setItems(itemsArray);
    };

    fetchItems();
  }, []);

  return (
    <div className="classifieds-container">
      {items.map((item) => (
        <ItemCard
          key={item.id}
          item={item}
        />
      ))}
    </div>
  );
};
```

## Part 4: Wiring Components Together

Ensure that your `AddItemModal` is correctly wired to open from a button click in the UI, and that adding a new item through the modal successfully sends the data to Firestore. Verify that the `Classifieds` component fetches and displays these items dynamically upon addition.

## Part 5: Authentication Flow Enhancement and Component Update

Enhance the application's authentication flow to conditionally display content based on the user's authentication status. If users are not logged in, they should see the `SignIn` component with an option to navigate to the signup route. This implementation uses Next.js's `Link` for seamless routing.

### Updating the Home Component

Update the `Home` component within the classifieds route to include conditional rendering based on authentication status. This modification ensures that unauthenticated users are prompted to sign in or sign up, enhancing security and user experience.

```javascript
'use client';

import { useState, useEffect } from 'react';
import { getAuth, onAuthStateChanged } from 'firebase/auth';
import AddItemModal from '../components/AddItemModal';
import Classifieds from '../components/Classifieds';
import NavBar from '../components/NavArea';
import Signin from '../components/Signin'; // Ensure you have this component
import { Container, Button } from 'react-bootstrap';
import Sponsors from '../components/Sponsors';
import Link from 'next/link';

export default function Home() {
  const [modalShow, setModalShow] = useState(false);
  const [currentUser, setCurrentUser] = useState(null);

  useEffect(() => {
    const auth = getAuth();
    const unsubscribe = onAuthStateChanged(auth, (user) => {
      setCurrentUser(user);
    });
    return () => unsubscribe(); // Cleanup subscription
  }, []);

  if (!currentUser) {
    return (
      <main className="flex min-h-screen flex-col items-center justify-center p-24">
        <SignIn />
        <p className="mt-4">
          Don't have an account? <Link href="/signup">Sign up</Link>
        </p>
      </main>
    );
  }

  return (
    <main className="flex min-h-screen flex-col items-center justify-between p-24">
      <NavBar />
      <div className="d-flex flex-column">
        <Container>
          <Classifieds />
          <Button
            variant="primary"
            onClick={() => setModalShow(true)}
          >
            Add New Item
          </Button>

          <AddItemModal
            show={modalShow}
            handleClose={() => setModalShow(false)}
          />
        </Container>
        <Sponsors />
      </div>
    </main>
  );
}
```

### Instructions for the Instructor:

1. Ensure the Firebase Authentication is properly set up in your project.
2. Update the `Home` component as shown above. This component is a key part of the classifieds route.
3. The updated `Home` component now includes logic to check if a user is logged in. If not, it renders a `SignIn` component along with a link to the signup page.
4. Make sure you have a `SignIn` component and a signup page in your application. The `Link` component from Next.js is used for navigation, offering a better user experience by avoiding full page reloads.

By implementing these changes, you enhance the security and usability of your application, ensuring that users are authenticated before they can add or view classified listings.

## Conclusion

By the end of Day 3, you'll have integrated Firestore into your app for adding and displaying items in real-time. This functionality is core to the classifieds feature of the Community Market App, allowing users to interact with a live database.
