Here’s the updated version of the instructions, with reminders to commit changes after each test.

---

### Project Overview

In this project, you will build your own version of the **Cat App**. The goal is to create a single page that displays a cat image and additional information about the cat. You will work within the `src/pages/cat` directory and progressively build the page using mock data.

---

### Step-by-Step Instructions:

#### Step 1: Set Up the Basic Component

1. **Create a directory**:
   - Inside the `src/pages` directory, create a subdirectory called `cat`.
   - Inside `src/pages/cat`, create a file called `index.js`.
   
2. **Create a `Cat` component**:
   - Add the following code to `src/pages/cat/index.js`:
   ```javascript
   // src/pages/cat/index.js
   export default function Cat() {
     return <h1>Hi, I'm a cat.</h1>;
   }
   ```

#### Step 1 (Test):
- Visit `http://localhost:3000/cat` in your browser. You should see the text "Hi, I'm a cat."
  
**Reminder**: Commit your changes to keep your progress safe!

---

#### Step 2: Import Mock Data

1. **Import the mock data**:
   - Import the cat data from `data/cat-data.json` into your `src/pages/cat/index.js` file:
   ```javascript
   // src/pages/cat/index.js
   import catData from '../../data/cat-data.json';
   ```

2. **Log the data**:
   - Log the `catData` object to the console to verify that the data is imported correctly:
   ```javascript
   console.log(catData);
   ```

#### Step 2 (Test):
- Open your browser to `http://localhost:3000/cat` and check the console to ensure the `catData` object is being logged correctly.

**Reminder**: Commit your changes to keep your progress safe!

---

#### Step 3: Create the `CatImage` Component

1. **Create a `CatImage` component**:
   - Inside `src/pages/cat`, create a new file called `CatImage.js`.
   - Add the following code to display the cat image:
   ```javascript
   // src/pages/cat/CatImage.js
   export default function CatImage(props) {
     const imgURL = props.catData.image_link;
     return <img src={imgURL} alt="Cat" />;
   }
   ```

2. **Import `CatImage` into `index.js`**:
   - Import the `CatImage` component into `src/pages/cat/index.js` and pass the `catData` object as a prop:
   ```javascript
   // src/pages/cat/index.js
   import catData from '../../data/cat-data.json';
   import CatImage from './CatImage';

   export default function Cat() {
     return (
       <div>
         <h1>Hi, I'm a cat.</h1>
         <CatImage catData={catData} />
       </div>
     );
   }
   ```

#### Step 3 (Test):
- Visit `http://localhost:3000/cat` and confirm that the cat image is displayed on the page.

**Reminder**: Commit your changes to keep your progress safe!

---

#### Step 4: Continue Building the Page

- **Extend the functionality**:
  - Add more components to display additional information (such as the cat's name, breed, or description) using the mock data from `cat-data.json`.
  - For example, create a `CatDetails` component that shows the cat’s name and breed.

- **Test frequently**:
  - After adding each component, test the application by visiting `http://localhost:3000/cat` to ensure everything works correctly.

**Reminder**: Commit your changes to keep your progress safe after each test!

---

By the end of this project, you will have:
- Set up a **Next.js** page that displays a cat image and related information using mock data.
- Practiced importing data and creating reusable components in **React**.
- Applied **component-based architecture** to structure a webpage effectively.

---

Now, with a reminder to commit your changes after each test, this will help you safeguard your progress while building the Cat App!