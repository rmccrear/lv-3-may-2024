# Day 4: Implementing Delete Functionality with User Authentication

Day 4 focuses on implementing the delete functionality for items posted in our Community Market App. This feature allows users to delete their own items, ensuring they are logged in and are the original poster of the item.

## Part 1: Setting Up Delete Functionality

### Update the ItemCard Component

First, let's add a delete button to each item card, but it should only be visible to the user who posted the item.

1. Import necessary functions and hooks from Firebase and React.

```js
import React, { useState, useEffect } from 'react';
import { doc, deleteDoc } from 'firebase/firestore';
import { db } from '../firebaseConfig';
import { getAuth, onAuthStateChanged } from 'firebase/auth';
```

2. Modify the `ItemCard` component to manage the current user state with `useState` and `useEffect`.

```js
const [user, setUser] = useState(null);

useEffect(() => {
  const auth = getAuth();
  const unsubscribe = onAuthStateChanged(auth, (currentUser) => {
    setUser(currentUser);
  });

  return () => unsubscribe();
}, []);
```

3. Add a delete button to the card that calls a `handleDelete` function when clicked. Ensure this button is only shown to the user who posted the item.

```js
{
  user && user.uid === item.userId && (
    <button className="delete-button" onClick={() => handleDelete(item.id)}>
      Delete
    </button>
  );
}
```

4. Implement the `handleDelete` function within the `ItemCard` component.

```js
const handleDelete = async (itemId) => {
  if (window.confirm('Are you sure you want to delete this item?')) {
    await deleteDoc(doc(db, 'items', itemId));
    window.location.reload(); // Refresh the page to update the item list
  }
};
```

## Part 2: Securing the Delete Operation

### Firestore Security Rules Update

Ensure your Firestore security rules allow users to delete only their items by updating the rules in the Firebase console.

```sh
service cloud.firestore {
  match /databases/{database}/documents {
    match /items/{itemId} {
      allow read, write: if request.auth.uid == resource.data.userId;
    }
  }
}
```

### Instructions for the Instructor:

1. Start by explaining the importance of securing user operations in web applications, highlighting the delete functionality as a critical aspect of user data management.
2. Guide the students through the steps to update the `ItemCard` component, especially the transition from `useAuthState` to `useState` and `useEffect` for managing user authentication state. Explain the code changes and their purpose, particularly the conditional rendering to display the delete button only for the item's owner.
3. Discuss the Firestore security rules update, explaining how these rules help prevent unauthorized delete operations and secure user data.
4. Demonstrate a live coding session, showing the complete process of implementing the delete functionality, from updating the component to testing the feature with different user accounts.
5. Encourage students to ask questions and share their screens if they encounter issues, fostering a collaborative learning environment.

## Conclusion

By the end of Day 4, students will have implemented a secure delete functionality in the Community Market App, reinforcing their understanding of user authentication and authorization in web applications. This feature enhances the app's usability and security, allowing users to manage their posted items effectively.
