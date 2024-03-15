## Day 4, Hour 1: Setting Up Real-Time Firestore in React

This session covers setting up Firestore for real-time updates in a React application. We'll replicate the initial setup from Day 3 and introduce components that subscribe to real-time updates.

### Setting Up Firestore

Just like in Day 3, start by setting up Firestore in your Next.js project.

1. **Install Firebase SDK**:
   Check Day 3 for instructions, Use the same `firebase.js` as yesterday

### Creating Components for Real-Time CRUD Operations

We will create components similar to Day 3 but with real-time data synchronization.

#### Step 1: Creating a Document with Real-Time Updates

First, let's start with creating todos.

- **Location**: `src/app/components/TodoForm.jsx`

```jsx
// Same as yesterday
'use client';
import React, { useState } from 'react';
import { db } from '../firebaseConfig';
import { collection, addDoc } from 'firebase/firestore';

const TodoForm = () => {
  const [title, setTitle] = useState('');
  const [description, setDescription] = useState('');

  const handleSubmit = async (e) => {
    e.preventDefault();
    try {
      await addDoc(collection(db, 'todos'), {
        title,
        description,
        completed: false,
      });
      setTitle('');
      setDescription('');
    } catch (error) {
      console.error('Error adding todo: ', error);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <div>
        <label htmlFor="title">Title</label>
        <input
          type="text"
          id="title"
          value={title}
          onChange={(e) => setTitle(e.target.value)}
          required
        />
      </div>
      <div>
        <label htmlFor="description">Description</label>
        <input
          type="text"
          id="description"
          value={description}
          onChange={(e) => setDescription(e.target.value)}
          required
        />
      </div>
      <button type="submit">Add Todo</button>
    </form>
  );
};

export default TodoForm;
```

In the next hour, we'll continue with reading, updating, and deleting documents with real-time updates.

<!--! Hour 2  -->

## Day 4, Hour 2: Real-Time Data Operations in Firestore

In this hour, we'll enhance our React app with the ability to perform CRUD operations with real-time updates from Firestore.

### Step 2: Reading Documents in Real-Time

Modify the `TodoList` component to subscribe to real-time updates from the Firestore database.

- **Location**: `src/app/components/TodoList.jsx`

```jsx
// This is different for live updates
import React, { useEffect, useState } from 'react';
import { collection, onSnapshot } from 'firebase/firestore';
import { db } from '../firebaseConfig';
import DeleteTodoButton from './DeleteTodoButton';
import UpdateTodoForm from './UpdateTodoForm';

const TodoList = () => {
  const [todos, setTodos] = useState([]);

  useEffect(() => {
    // onSnapshot: when finished listening for data returns a function named "unsubscribe" This is why we name the variable unsubscribe.
    const unsubscribe = onSnapshot(collection(db, 'todos'), (snapshot) => {
      const todosArray = snapshot.docs.map((doc) => ({
        id: doc.id,
        ...doc.data(),
      }));
      setTodos(todosArray);
    });

    return () => unsubscribe(); // This variable isn't calling the onSnapshot method (we didnt pass reference, we invoked it), its calling the method thats returned by the onSnapshot method to stop listening.
  }, []);

  return (
    <div>
      <h2>Todos</h2>
      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>
            <h3>{todo.title}</h3>
            <p>{todo.description}</p>
            <UpdateTodoForm todo={todo} />
            <DeleteTodoButton id={todo.id} />
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoList;
```

### Step 3: Updating Documents in Real-Time

Next, let's adjust the `UpdateTodoForm` component to update todos in real-time.

- **Location**: `src/app/components/UpdateTodoForm.jsx`

```jsx
import React, { useState } from 'react';
import { doc, updateDoc } from 'firebase/firestore';
import { db } from '../firebaseConfig';

const UpdateTodoForm = ({ todo }) => {
  const [title, setTitle] = useState(todo.title);
  const [description, setDescription] = useState(todo.description);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const todoRef = doc(db, 'todos', todo.id);

    try {
      await updateDoc(todoRef, {
        title,
        description,
      });
    } catch (error) {
      console.error('Error updating todo: ', error);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={title}
        onChange={(e) => setTitle(e.target.value)}
        placeholder="Title"
      />
      <input
        type="text"
        value={description}
        onChange={(e) => setDescription(e.target.value)}
        placeholder="Description"
      />
      <button type="submit">Update</button>
    </form>
  );
};

export default UpdateTodoForm;
```

### Step 4: Deleting Documents in Real-Time

Finally, update the `DeleteTodoButton` component to reflect deletions in real-time.

- **Location**: `src/app/components/DeleteTodoButton.jsx`

```jsx
import React from 'react';
import { doc, deleteDoc } from 'firebase/firestore';
import { db } from '../firebaseConfig';

const DeleteTodoButton = ({ id }) => {
  const handleDelete = async () => {
    const todoRef = doc(db, 'todos', id);

    try {
      await deleteDoc(todoRef);
    } catch (error) {
      console.error('Error deleting todo: ', error);
    }
  };

  return <button onClick={handleDelete}>Delete</button>;
};

export default DeleteTodoButton;
```

This setup ensures that your application reflects updates to the Firestore database in real-time. Changes made to todo items, whether they are additions, updates, or deletions, will immediately be visible in the UI without needing to refresh the page.
