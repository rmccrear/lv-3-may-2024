# Day 2: Firebase Integration and Component Testing

Day 2 focuses on integrating Firebase for authentication and data storage, alongside creating and testing essential components with sample data.

## Part 1: Firebase Setup

### Firebase Authentication and Firestore

- **Firebase Authentication**: Securely manage user signups and logins.
- **Firestore**: A NoSQL database for storing user and item data.

### Initial Setup

1. Create a Firebase project in the Firebase console.
2. Add Firebase to your application:

```bash
npm install firebase
```

3. Initialize Firebase in your project:

```js
// Import the functions you need from the SDKs you need
import { initializeApp } from 'firebase/app';

import { getAuth } from 'firebase/auth';
import { getFirestore } from 'firebase/firestore';

const firebaseConfig = {
  apiKey: 'AIzaSyB9dwC0FUqMLEL6cFArZOrcanF6cxsbMDk',
  authDomain: 'todo-test-a09b2.firebaseapp.com',
  projectId: 'todo-test-a09b2',
  storageBucket: 'todo-test-a09b2.appspot.com',
  messagingSenderId: '1017452605758',
  appId: '1:1017452605758:web:a63bcfd9f970842d5f7c6f',
};

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
const db = getFirestore(app);
```

## Part 2: Creating Authentication Components

### Signup Component

For testing purposes before integration, simulate the signup process using static data.

- **Sample Signup Data**:

  ```json
  {
    "userId": "user789",
    "name": "Alex Doe",
    "location": "San Francisco, CA",
    "contact": {
      "email": "alexdoe@example.com",
      "phone": "(555) 123-4567"
    },
    "joinedDate": "2024-03-28T12:00:00.000Z",
    "bio": "Lover of vintage furniture and refurbished tech. Here to find great deals and connect with the community.",
    "profilePicture": "https://example.com/images/profile/user789.jpg"
  }
  ```

- **Signup Component JSX**:

  ```javascript
  import React, { useState } from 'react';

  const Signup = () => {
    // Sample state setup for form fields, replace with useState hooks in your app
    const [email, setEmail] = useState('');
    const [password, setPassword] = useState('');

    const handleSubmit = (e) => {
      e.preventDefault();
      // Firebase signup logic here
    };

    return (
      <form onSubmit={handleSubmit}>
        <input
          type="email"
          value={email}
          onChange={(e) => setEmail(e.target.value)}
          placeholder="Email"
          required
        />
        <input
          type="password"
          value={password}
          onChange={(e) => setPassword(e.target.value)}
          placeholder="Password"
          required
        />
        <button type="submit">Sign Up</button>
      </form>
    );
  };

  export default Signup;
  ```

- **Signin Component JSX**:

  ```js
  import React, { useState } from 'react';
  import { getAuth, signInWithEmailAndPassword } from 'firebase/auth';

  const SignIn = () => {
    const [email, setEmail] = useState('');
    const [password, setPassword] = useState('');
    const auth = getAuth();

    const handleSubmit = async (e) => {
      e.preventDefault();
      try {
        const userCredential = await signInWithEmailAndPassword(
          auth,
          email,
          password,
        );
        // User signed in
        console.log('User signed in:', userCredential.user);
      } catch (error) {
        console.error('Error signing in:', error);
      }
    };

    return (
      <div className="signin-container">
        <h2>Sign In</h2>
        <form onSubmit={handleSubmit}>
          <div className="form-group">
            <label htmlFor="email">Email</label>
            <input
              type="email"
              id="email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              placeholder="Enter your email"
              required
            />
          </div>
          <div className="form-group">
            <label htmlFor="password">Password</label>
            <input
              type="password"
              id="password"
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              placeholder="Enter your password"
              required
            />
          </div>
          <button
            type="submit"
            className="signin-button"
          >
            Sign In
          </button>
        </form>
      </div>
    );
  };

  export default SignIn;
  ```

### Login Component

- Implement the login functionality similarly, focusing on email and password authentication.

## Part 3: Testing with Sample Item Data

Before Firestore integration, test displaying items with provided JSON data.

- **Sample Item Data**:

  ```json
  {
    "itemId": "123456",
    "sellerId": "user789",
    "title": "Vintage Wooden Chair",
    "description": "A beautifully crafted vintage wooden chair in excellent condition. Perfect for adding a touch of classic elegance to your living space.",
    "price": 75.0,
    "category": "Furniture",
    "images": [
      "https://example.com/images/items/item123456-1.jpg",
      "https://example.com/images/items/item123456-2.jpg"
    ],
    "postedDate": "2024-03-28T12:00:00.000Z",
    "condition": "Used - Like New",
    "tags": ["vintage", "wood", "furniture", "chair"]
  }
  ```

- Implement components to display this data, such as an `ItemCard` component for showcasing individual listings.

## Extending Day 2: Building Classifieds Page Components

In addition to integrating Firebase and creating authentication components, we'll expand our application to include components for displaying classified listings. Using the sample item data, we'll demonstrate rendering multiple products on a classifieds page.

## Creating Item Components

### ItemCard Component

First, create an `ItemCard` component to display the details of a single item. This component will be reusable for each product listing on the classifieds page.

```javascript
import React from 'react';

const ItemCard = ({ item }) => {
  return (
    <div className="item-card">
      <img
        src={item.images[0]}
        alt={item.title}
        style={{ width: '100%', height: 'auto' }}
      />
      <h3>{item.title}</h3>
      <p>{item.description}</p>
      <p>Price: ${item.price.toFixed(2)}</p>
      <p>Condition: {item.condition}</p>
    </div>
  );
};
```

### Classifieds Component

Next, create a `Classifieds` component that uses the `ItemCard` component to display a list of items. For demonstration purposes, replicate the sample item data to simulate multiple listings.

```javascript
import React from 'react';
import ItemCard from './ItemCard'; // Adjust the import path based on your project structure

const sampleItems = [
  // Repeat the sample item JSON data here as many times as needed, with minor adjustments for variety if desired
];

const Classifieds = () => {
  return (
    <div className="classifieds-container">
      {sampleItems.map((item, index) => (
        <ItemCard
          key={index}
          item={item}
        />
      ))}
    </div>
  );
};
```

Ensure to import and use the `Classifieds` component in your application where you intend to display the classified listings.

## Integration Steps

1. Add the `ItemCard` and `Classifieds` components to your project.
2. Use the provided sample item data, duplicating it within the `Classifieds` component to simulate multiple listings.
3. Integrate the `Classifieds` component into your application's page where you plan to display the classifieds listings.

This setup allows you to showcase a basic classifieds page with listings, ready to be enhanced with dynamic data fetching from Firestore in the next steps of development.

## Create Modal for adding item

```js
import React, { useState } from 'react';
import Modal from 'react-bootstrap/Modal';
import Button from 'react-bootstrap/Button';
import Form from 'react-bootstrap/Form';

const AddItemModal = ({ show, handleClose }) => {
  const [title, setTitle] = useState('');
  const [description, setDescription] = useState('');
  const [price, setPrice] = useState('');
  const [category, setCategory] = useState('');
  const [condition, setCondition] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    // Here, you would handle the addition of the new item.
    // For demonstration, we're just logging to the console.
    console.log({ title, description, price, category, condition });
    handleClose(); // Close the modal
  };

  return (
    <Modal
      show={show}
      onHide={handleClose}
    >
      <Modal.Header closeButton>
        <Modal.Title>Add New Item</Modal.Title>
      </Modal.Header>
      <Modal.Body>
        <Form onSubmit={handleSubmit}>
          <Form.Group
            className="mb-3"
            controlId="itemTitle"
          >
            <Form.Label>Title</Form.Label>
            <Form.Control
              type="text"
              placeholder="Enter item title"
              value={title}
              onChange={(e) => setTitle(e.target.value)}
              required
            />
          </Form.Group>
          <Form.Group
            className="mb-3"
            controlId="itemDescription"
          >
            <Form.Label>Description</Form.Label>
            <Form.Control
              as="textarea"
              rows={3}
              placeholder="Enter item description"
              value={description}
              onChange={(e) => setDescription(e.target.value)}
              required
            />
          </Form.Group>
          <Form.Group
            className="mb-3"
            controlId="itemPrice"
          >
            <Form.Label>Price</Form.Label>
            <Form.Control
              type="number"
              placeholder="Enter item price"
              value={price}
              onChange={(e) => setPrice(e.target.value)}
              required
            />
          </Form.Group>
          <Form.Group
            className="mb-3"
            controlId="itemCategory"
          >
            <Form.Label>Category</Form.Label>
            <Form.Control
              type="text"
              placeholder="Enter item category"
              value={category}
              onChange={(e) => setCategory(e.target.value)}
              required
            />
          </Form.Group>
          <Form.Group
            className="mb-3"
            controlId="itemCondition"
          >
            <Form.Label>Condition</Form.Label>
            <Form.Select
              value={condition}
              onChange={(e) => setCondition(e.target.value)}
              required
            >
              <option value="">Select condition</option>
              <option value="New">New</option>
              <option value="Used - Like New">Used - Like New</option>
              <option value="Used - Good">Used - Good</option>
              <option value="Used - Acceptable">Used - Acceptable</option>
            </Form.Select>
          </Form.Group>
          <Button
            variant="primary"
            type="submit"
          >
            Submit
          </Button>
        </Form>
      </Modal.Body>
    </Modal>
  );
};

export default AddItemModal;
```
