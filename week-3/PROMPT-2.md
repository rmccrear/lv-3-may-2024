
## Setup:

Setup will require you to crete a next.js app and add tailwind to the project. Test at each step. Set aside some time to make this work. If you get stuck for beyond 10-15 minutes, ask for help! You may want to try this more than once to get the hang of it and retain the information.

Step 1: Create a next.js project with the following command:
```bash
npx create-next-app@latest
```

Step 1 (test): cd into the project directory and start the development server with the following command and visit `http://localhost:3000` in your browser. You should see the default Next.js landing page.
```bash
cd <project-directory>
npm run dev
```

Step 2: delete the contents of `src/pages/index.js` and replace it with a simple Home component. For example:
```javascript
// src/pages/index.js
export default function Home() {
  return <h1>Welcome to the Cat App!</h1>;
}
```

Step 2 (test): Visit `http://localhost:3000` in your browser. You should see the text "Welcome to the Cat App!".

Step 3: Add tailwind. See the guide for next.js. (https://tailwindcss.com/docs/guides/nextjs)[https://tailwindcss.com/docs/guides/nextjs]

Step 3 (test): Add a tailwind class to the `h1` element in the `src/pages/index.js` file. For example:
```javascript
// src/pages/index.js
export default function Home() {
  return <h1 className="text-4xl text-center">Welcome to the Cat App!</h1>;
}
```

Step 4: Make a splash page using tailwind classes. Try out different classes to see how you can use tailwind instead of writing your own CSS.

### Now you are all set up to start the project!

## Project:

You will create your own version of the Cat App in . You will create a single page that displays a cat image and some information about the cat. You will stay in the `src/pages/cats` directory for this project. 

Step 1: Create a subdirectory in the `src/pages` directory called `cat`. And create a file called `index.js` inside the `src/pages/cat` directory. Create a Component called `Cat` that says "Hi, I'm a cat." You may start with the following code:

```javascript
// src/pages/cat/index.js
export default function Cat() {
  return <h1>Hi, I'm a cat.</h1>;
}
```

Step 1 (test): Visit `http://localhost:3000/cat` in your browser. You should see the text "Hi, I'm a cat."

Step 2: Import the mock data from `data/cat-data.json` into the `src/pages/cat/index.js` file. You may start with the following code:

```javascript
// src/pages/cat/index.js
import catData from '../../data/cat-data.json';
```

Step 2 (test): Log the `catData` object to the console to verify that the data is being imported correctly. Open your browser to `http://localhost:3000/cat` and check the console for the log.

Step 3: Create a CatImage component that displays the cat image from the mock data. You may start with the following code:

```javascript
// src/pages/cats/CatImage.js
export default function CatImage(props) {
  const imgURL = props.catData.image_link;
  return <img src={imgURL} alt="Cat" />;
}
```

Step 3 (test): Import the `CatImage` component into the `src/pages/cat/index.js` file and pass the `catData` object as a prop to the `CatImage` component. You should see the cat image displayed on the page.

You can use the following code as a starting point:

```javascript 
// src/pages/cat/index.js
import catData from '../../data/cat-data.json';
// import the CatImage component here
import CatImage from './CatImage';

export default function Cat() {
  return (
    <div>
      <h1>Hi, I'm a cat.</h1>
      {/*Add the CatImage component here*/}
      <CatImage catData={catData} />
    </div>
  );
}
```

Step 4: Contunue building the other components and the page as you see fit. Remember to test frequently and commit your changes often.