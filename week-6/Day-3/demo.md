## Day 3, Hour 1: Introduction to Firestore and Database Basics

Today, we're diving into databases, focusing on Firestore, a NoSQL database from Firebase. We'll compare SQL and NoSQL databases, discuss schemas, and the difference between local storage and databases. Finally, we'll set up a simple Firestore database for a basic application.

### Understanding Databases

Databases are structured systems for storing, retrieving, and managing data. There are two main types: SQL (relational) and NoSQL (non-relational).

- **SQL databases** use structured query language (SQL) for defining and manipulating data. They are organized into tables and are great for complex queries.
- **NoSQL databases**, like Firestore, are more flexible in terms of data structure, allowing for nested and varied data types. They're ideal for scalable applications and rapid development.

### What is a Schema?

A schema in a database is like a blueprint for data. It defines the structure of the data, much like a class in JavaScript defines the structure and behavior of an object. A schema specifies the fields in documents and their data types, ensuring data consistency.

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

### Creating a Simple Firestore Schema

Imagine you're building a todo application. Each todo item might have a title, description, and completion status. In Firestore, you would create a collection named `todos`, and each todo item would be a document within this collection with the specified fields.

### Conclusion

We've introduced Firestore and the basics of databases, covering the differences between SQL and NoSQL, the concept of schemas, and the advantages of using databases over local storage. Next, we'll dive into performing CRUD operations in Firestore, bringing these concepts into practice.

Remember, when designing your database schema or deciding between local storage and a database, consider your application's needs, data complexity, and growth potential.

## Day 3, Hour 2: CRUD Operations in Firestore with Documentation References

In this hour, we'll implement CRUD operations in Firestore within a Next.js project. Each operation is accompanied by references to the Firestore documentation for deeper exploration.

### Step 1: Creating Documents in Firestore

To add new items to your Firestore database, you'll use the `add` method. Here's a function to add todos:

```js
// In a file like utils/firestore.js
import { db } from './firebaseConfig';

export const addTodo = async (todo) => {
  try {
    const docRef = await db.collection('todos').add(todo);
    console.log('Document written with ID: ', docRef.id);
  } catch (error) {
    console.error('Error adding document: ', error);
  }
};
```

Reference the [Firestore Add a Document documentation](https://firebase.google.com/docs/firestore/manage-data/add-data#add_a_document) for more details on adding documents.

### Step 2: Reading Documents from Firestore

Fetching all items from a collection uses the `get` method:

```js
export const getTodos = async () => {
  try {
    const querySnapshot = await db.collection('todos').get();
    querySnapshot.forEach((doc) => {
      console.log(`${doc.id} => ${JSON.stringify(doc.data())}`);
    });
  } catch (error) {
    console.error('Error getting documents: ', error);
  }
};
```

For more information on reading documents, check the [Firestore Read Data documentation](https://firebase.google.com/docs/firestore/query-data/get-data).

### Step 3: Updating Documents in Firestore

Updating an item requires the `update` method, specifying the document's ID:

```js
export const updateTodo = async (id, updatedData) => {
  try {
    await db.collection('todos').doc(id).update(updatedData);
    console.log('Document successfully updated!');
  } catch (error) {
    console.error('Error updating document: ', error);
  }
};
```

See the [Firestore Update Documents documentation](https://firebase.google.com/docs/firestore/manage-data/add-data#update-data) for further details on updates.

### Step 4: Deleting Documents from Firestore

To remove an item, use the `delete` method:

```js
export const deleteTodo = async (id) => {
  try {
    await db.collection('todos').doc(id).delete();
    console.log('Document successfully deleted!');
  } catch (error) {
    console.error('Error removing document: ', error);
  }
};
```

Refer to the [Firestore Delete Documents documentation](https://firebase.google.com/docs/firestore/manage-data/delete-data) for more on deleting documents.

### Implementing Real-Time Data Fetching

Firestore allows for real-time data updates through the `onSnapshot` method:

```js
export const onTodosChange = (handleChange) => {
  db.collection('todos').onSnapshot((querySnapshot) => {
    const todos = [];
    querySnapshot.forEach((doc) => {
      todos.push({ id: doc.id, ...doc.data() });
    });
    handleChange(todos);
  });
};
```

For implementing real-time updates, consult the [Listen for Real-time Updates documentation](https://firebase.google.com/docs/firestore/query-data/listen).

### Conclusion

This hour introduced CRUD operations with Firestore in a Next.js app, alongside references to the official Firestore documentation. By incorporating these operations, your app can dynamically interact with database data, enhancing the user experience.

Next, we'll delve into more advanced Firestore features like querying and filtering data. Stay tuned for practical examples and documentation references!
