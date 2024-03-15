## Day 3, Hour 1: Introduction to Firestore and Database Basics

Today, we're diving into databases, focusing on Firestore, a NoSQL database from Firebase. We'll compare SQL and NoSQL databases, discuss schemas, and the difference between local storage and databases. Finally, we'll set up a simple Firestore database for a basic application.

### Understanding Databases

Databases are structured systems for storing, retrieving, and managing data. There are two main types: SQL (relational) and NoSQL (non-relational).
Here is a spreadsheet with examples showing the difference, and a snippet of SQL code to aggregate all the tables into one JOINED table (not required with nosql since its in JSON. Scroll down to see the JSON)
https://docs.google.com/spreadsheets/d/1rMVb5NAfZBKqa_rP9AV9DQF6ZK_Zj7U0w2Dx3u3Nwjw/edit#gid=140950084

- **SQL databases** use structured query language (SQL) for defining and manipulating data. They are organized into tables and are great for complex queries.
- **NoSQL databases**, like Firestore, are more flexible in terms of data structure, allowing for nested and varied data types. They're ideal for scalable applications and rapid development.

### What is a Schema?

A schema in a database is like a blueprint for data. It defines the structure of the data, much like a class in JavaScript defines the structure and behavior of an object. A schema specifies the fields in documents and their data types, ensuring data consistency.

Most NOSQL databases do not require a Schema like SQL does, but you can create logic to check for certain conditions if required. It would be like form validation.

### Local Storage vs. Database

Local storage provides a way to store data on the client's browser. It's great for saving small pieces of data but lacks the security, structure, and capacity of a database. Databases, on the other hand, are stored on servers, offering more storage, security, and data management features, making them suitable for dynamic applications that require data persistence and real-time updates.

### Setting Up Firestore in Your Next.js Project

1. **Create a Firebase Project**: If you haven't already, go to the Firebase Console, create a new project, and add your Next.js application to it.

2. **Enable Firestore**: Navigate to the "Firestore Database" section in the Firebase Console and click "Create database". Choose "Start in test mode" for now.

3. **Install Firebase SDK**:
   Ensure Firebase is installed in your Next.js project. If not, run:

   ```bash
   npm install firebase
   ```

4. **Initialize Firestore**:
   Create a `firebaseConfig.js` file to initialize Firebase and Firestore. Replace the configuration object with your project's settings.

   ```js
   import firebase from 'firebase/app';
   import 'firebase/firestore';

   const firebaseConfig = {
     apiKey: 'YOUR_API_KEY',
     authDomain: 'YOUR_AUTH_DOMAIN',
     projectId: 'YOUR_PROJECT_ID',
     storageBucket: 'YOUR_STORAGE_BUCKET',
     messagingSenderId: 'YOUR_MESSAGING_SENDER_ID',
     appId: 'YOUR_APP_ID',
   };

   if (!firebase.apps.length) {
     firebase.initializeApp(firebaseConfig);
   } else {
     firebase.app(); // if already initialized, use that one
   }

   export const db = firebase.firestore();
   ```

## Understanding Firestore Security Rules

When you initialize a new Firestore database in test mode, Firebase sets up default security rules that allow open access to the database. This setup is designed to help you get started quickly, but it's important to understand what these rules mean and how to evolve them for your application's security.

### Default Test Mode Rules

By default, your Firestore security rules might look something like this:

```sh
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    // This rule allows anyone with your Firestore database reference to view, edit,
    // and delete all data in your Firestore database. It is useful for getting
    // started, but it is configured to expire after 30 days because it
    // leaves your app open to attackers. At that time, all client
    // requests to your Firestore database will be denied.
    //
    // Make sure to write security rules for your app before that time, or else
    // all client requests to your Firestore database will be denied until you update
    // your rules.
    match /{document=**} {
      allow read, write: if request.time < timestamp.date(2024, 4, 14);
    }
  }
}
```

### Key Takeaways

- **Open Access for Testing**: The default rules grant read and write access to everyone. This is fine for initial development and testing but not suitable for a production environment.
- **Expiration Date**: Note the expiration date set within the rule (`timestamp.date(2024, 4, 14)`). After this date, all client requests to read or write will be denied unless you update your rules.
- **Security Implications**: While these open rules are convenient for development, they leave your database vulnerable to unauthorized access. Before moving to production, you'll need to implement more restrictive rules based on your app's requirements.

### Next Steps

Before the expiration date, you should define more specific security rules to protect your data. Firestore rules can control access based on authentication, validate data types, and more. For a test app, ensure you update these rules to avoid losing access or exposing sensitive information.

This introduction to Firestore security rules is just the beginning. As you develop your application, consider diving deeper into [Firestore's security rules documentation](https://firebase.google.com/docs/firestore/security/get-started) to learn how to tailor rules to your specific needs.

### Creating a Simple Firestore Schema

Imagine you're building a todo application. Each todo item might have a title, description, and completion status. In Firestore, you would create a collection named `todos`, and each todo item would be a document within this collection with the specified fields.

### Conclusion

We've introduced Firestore and the basics of databases, covering the differences between SQL and NoSQL, the concept of schemas, and the advantages of using databases over local storage. Next, we'll dive into performing CRUD operations in Firestore, bringing these concepts into practice.

Remember, when designing your database schema or deciding between local storage and a database, consider your application's needs, data complexity, and growth potential.

<!--! Hour 2  -->

## Day 3, Hour 2: CRUD Operations in Firestore with Documentation References

In this hour, we'll integrate CRUD operations in Firestore within a Next.js project, enhancing our app with dynamic data interaction capabilities. Each step is detailed below, including references to Firestore documentation for a deeper understanding.

### CRUD Operations

#### Step 1: Creating Documents in Firestore

Create a function to add documents to your Firestore collection:

- **Location**: `src/app/utils/firestore.js`
  <!-- Copied from docs -->

  ```js
  import { collection, addDoc } from 'firebase/firestore';

  // Add a new document with a generated id.
  const docRef = await addDoc(collection(db, 'cities'), {
    name: 'Tokyo',
    country: 'Japan',
  });
  console.log('Document written with ID: ', docRef.id);
  ```

```js
import { db } from '../firebaseConfig';
import { collection, addDoc } from 'firebase/firestore';
// convert to this:
export const addTodo = async (todo) => {
  const docRef = await addDoc(collection(db, 'todos'), todo);
  console.log('Document written with ID: ', docRef.id);
};
```

#### Add a React component to create Todo

- **Location**: Create a new component `src/app/components/TodoForm.jsx`

```jsx
'use client';
import React, { useState } from 'react';
import { addTodo } from '../utils/firestore';

const TodoForm = () => {
  const [title, setTitle] = useState('');
  const [description, setDescription] = useState('');

  const handleSubmit = async (e) => {
    e.preventDefault();
    try {
      await addTodo({
        title: title,
        description: description,
      });
      console.log('Todo added successfully');
      setTitle('');
      setDescription('');
    } catch (error) {
      console.error('Error adding document: ', error);
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

- **Reference**: [Add a Document](https://firebase.google.com/docs/firestore/manage-data/add-data#add_a_document)

Encourage to explore docs and build apps that use other methods of adding things.

#### Step 2: Reading Documents from Firestore

To fetch all items from your Firestore collection and render them in your React component, you can use the Firestore modular SDK. Here's how you can implement this in a component with a `useEffect` hook:

- **Location**: Create a new component `src/app/components/TodoList.jsx`

```jsx
import React, { useEffect, useState } from 'react';
import { collection, getDocs } from 'firebase/firestore';
import { db } from '../firebaseConfig';

const TodoList = () => {
  const [todos, setTodos] = useState([]);

  useEffect(() => {
    const fetchTodos = async () => {
      const querySnapshot = await getDocs(collection(db, 'todos'));
      const todosArray = [];
      querySnapshot.forEach((doc) => {
        // Pushing document data and id into an array
        todosArray.push({ id: doc.id, ...doc.data() });
      });
      setTodos(todosArray);
    };

    fetchTodos();
  }, []);

  return (
    <div>
      <h2>Todos</h2>
      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>
            {todo.title} - {todo.completed ? 'Completed' : 'Pending'}
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoList;
```

- **Reference**: [Read Data](https://firebase.google.com/docs/firestore/query-data/get-data#get_all_documents_in_a_collection)

<!--! Hour 3  -->

#### Step 3: Updating Documents in Firestore

To update specific documents in your Firestore collection, utilize the Firestore modular SDK's `doc` and `updateDoc` methods. Here's a practical example within a React component:

- **Location**: `src/app/utils/firestore.js`

  ```js
  import { doc, updateDoc } from 'firebase/firestore'; // Add to existing import

  export const updateTodo = async (id, updatedData) => {
    const todoRef = doc(db, 'todos', id);
    try {
      await updateDoc(todoRef, updatedData);
      console.log('Document successfully updated!');
    } catch (error) {
      console.error('Error updating document: ', error);
    }
  };
  ```

  Create a new component to update a todo item's title and description. This component will use the `updateTodo` function from your utility functions to perform the update operation in Firestore.

- **Location**: `src/app/components/UpdateTodo.jsx`

```jsx
import React, { useState } from 'react';
import { updateTodo } from '../utils/firestore';

const UpdateTodo = ({ todo }) => {
  const [title, setTitle] = useState(todo.title);
  const [description, setDescription] = useState(todo.description);

  const handleSubmit = async (e) => {
    e.preventDefault();
    try {
      await updateTodo(todo.id, {
        title,
        description,
      });
      console.log('Todo updated successfully');
    } catch (error) {
      console.error('Error updating todo: ', error);
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
      <button type="submit">Update Todo</button>
    </form>
  );
};

export default UpdateTodo;
```

Incorporate this component into your application where you manage todo items. This will enable users to update the title and description of existing todos.

**Location** Inside the TodoList component:

```jsx
return (
  <div>
    <h2>Todos</h2>
    <ul>
      {todos.map((todo) => (
        <li key={todo.id}>
          <h2>{todo.title}</h2>
          <p>{todo.description}</p>
          <UpdateTodo todo={todo} /> ADD THIS LINE
        </li>
      ))}
    </ul>
  </div>
);
```

- **Reference**: [Update a Document](https://firebase.google.com/docs/firestore/manage-data/add-data#update-data)

#### Step 4: Deleting Documents from Firestore

Deleting documents from your Firestore collection can be achieved using the `doc` and `deleteDoc` methods from the Firestore modular SDK. Implement it as follows:

- **Location**: `src/app/utils/firestore.js`

  ```js
  import { doc, deleteDoc } from 'firebase/firestore'; // Add to existing imports

  export const deleteTodo = async (id) => {
    const todoRef = doc(db, 'todos', id);
    try {
      await deleteDoc(todoRef);
      console.log('Document successfully deleted!');
    } catch (error) {
      console.error('Error removing document: ', error);
    }
  };
  ```

- **Reference**: [Delete a Document](https://firebase.google.com/docs/firestore/manage-data/delete-data)
  Create a new component that acts as a button for deleting a todo item. This button will be used inside each list item (`<li>`) to provide a way to delete todos directly from your list.

- **Location**: `src/app/components/DeleteTodoButton.jsx`

```jsx
import React from 'react';
import { deleteTodo } from '../utils/firestore';

const DeleteTodoButton = ({ id }) => {
  const handleDelete = async () => {
    try {
      await deleteTodo(id);
      console.log('Todo deleted successfully');
      // Optionally, trigger a state update to refresh the list
    } catch (error) {
      console.error('Error deleting todo: ', error);
    }
  };

  return <button onClick={handleDelete}>Delete</button>;
};

export default DeleteTodoButton;
```

To integrate this button into your todo list, modify your `TodoList.jsx` component to include the `DeleteTodoButton` component inside each list item. Ensure you pass the `id` of the todo as a prop to `DeleteTodoButton`.

Here's an example modification to your existing `TodoList` component:

```jsx
// Within TodoList.jsx, include the DeleteTodoButton component
import DeleteTodoButton from './DeleteTodoButton';

// Inside your map function, nest DeleteTodoButton inside each <li>
return (
  <div>
    <h2>Todos</h2>
    <ul>
      {todos.map((todo) => (
        <li key={todo.id}>
          <h2>{todo.title}</h2>
          <p>{todo.description}</p>
          <DeleteTodoButton id={todo.id} /> // ADD THIS LINE
          <UpdateTodo todo={todo} />
        </li>
      ))}
    </ul>
  </div>
);
```

This setup allows each todo item in your list to have an associated delete button. When clicked, the button will call the `deleteTodo` function to remove the item from Firestore, leveraging the modular SDK's functionality.
