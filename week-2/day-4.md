### Key Points:
- **Create a 3-page Next.js site**: Splash page, About page, and Gallery page.
- **Use Bootstrap for styling**.
- **Place static images** in the `public/` directory.
- **Bonus**: Use **cowsay** and custom CSS.

---

### Assignment: Build a Three-Page Website with Next.js

#### Objective:
In this assignment, you will create a **three-page website** using **Next.js**. The site will include a **splash page**, an **about page**, and a **gallery page**. The pages will be styled using **Bootstrap**, and you will manage static images from the **`public/`** directory. For a bonus, you can integrate the **cowsay** library and create custom styles using CSS files.

---

### Pages to Create:

1. **Splash Page** (`src/pages/index.js`):
   - A landing page featuring a large background image.
   - This page should display a welcome message.
   
2. **About Page** (`src/about/index.js`):
   - A page with information about you (or a fictional person/company), containing text, an image, and a list of facts/achievements.

3. **Gallery Page** (`src/gallery/index.js`):
   - A page displaying at least **6 images** in a grid layout.
   - Images should come from sources such as **Pexels.com**, **AI-generated** images, or other royalty-free sources.

---

### Requirements:

1. **Set Up a New Next.js Project**:
   - Use `create-next-app` to generate the initial project structure.

2. **Install and Import Bootstrap**:
   - Install Bootstrap in your project and import it into your pages for styling.

3. **Splash Page** (`src/pages/index.js`):
   - Create a large background image and a welcome message styled with Bootstrap.
   - Use the `public/` directory for storing static images.
     - Example: Place your splash image in `public/splash-image.jpg`.

4. **About Page** (`src/about/index.js`):
   - Include a heading, text, an image, and a list of facts or achievements.
   - Use Bootstrap for styling.

5. **Gallery Page** (`src/gallery/index.js`):
   - Display at least **6 images** in a grid layout using Bootstrap grid classes.
   - Store gallery images in the `public/` folder and reference them using relative paths (e.g., `/gallery/img1.jpg`).

---

### Bonus (Optional):

1. **Cowsay Integration (Optional)**:
   - Add **cowsay** to your **About Page** for fun. Install cowsay with:
     ```bash
     npm install cowsay
     ```
   - Import and use it on the About page.

2. **Custom CSS**:
   - Create your own CSS styles and apply them to your pages. Place your styles in the `styles` directory and import them into your pages.

---

### Steps to Complete:

1. **Set Up Your Project**:
   - Create a new Next.js project:
     ```bash
     npx create-next-app@latest my-three-page-site
     cd my-three-page-site
     ```

2. **Install Bootstrap**:
   - Install Bootstrap:
     ```bash
     npm install bootstrap
     ```

3. **Import Bootstrap**:
   - Import Bootstrap in the required pages:
     ```javascript
     import 'bootstrap/dist/css/bootstrap.min.css';
     ```

4. **Create the Pages**:

   - **Splash Page** (`src/pages/index.js`):
     - Add a large image from `public/` and a welcome message.

     Example code for Splash Page:
     ```jsx
     import 'bootstrap/dist/css/bootstrap.min.css';

     export default function HomePage() {
       return (
         <div className="container-fluid text-center" style={{ backgroundImage: 'url(/splash-image.jpg)', height: '100vh' }}>
           <h1 className="display-3 text-white">Welcome to My Website</h1>
         </div>
       );
     }
     ```

   - **About Page** (`src/about/index.js`):
     - Add text, image, and list, styled with Bootstrap.
   
   - **Gallery Page** (`src/gallery/index.js`):
     - Display at least 6 images in a grid layout using Bootstrap classes.

5. **Place Static Images**:
   - Place all your static images (e.g., for the splash and gallery pages) in the `public/` directory.
   - You can reference images like so: `url('/splash-image.jpg')` or `<img src="/gallery/img1.jpg" />`.

---

### Example Page Structure:

```
my-three-page-site/
│
├── public/
│   ├── splash-image.jpg
│   ├── gallery/
│   │   ├── img1.jpg
│   │   ├── img2.jpg
│   │   ├── img3.jpg
│   │   ├── img4.jpg
│   │   ├── img5.jpg
│   │   └── img6.jpg
│
├── src/
│   ├── pages/
│   │   └── index.js
│   ├── about/
│   │   └── index.js
│   ├── gallery/
│   │   └── index.js
│
├── styles/
│   └── custom.css  (optional)
```

---

### Submission Guidelines:

1. **Create a GitHub Repository**:
   - Push your project to a new GitHub repository.

2. **Turn In the Assignment**:
   - Submit the **link to your GitHub repository** on the class Moodle.

---

### Example Workflow:

1. **Run the Next.js Development Server**:
   - Start the development server to view your pages live:
     ```bash
     npm run dev
     ```

2. **View the Pages**:
   - Visit the following URLs to check your pages:
     - `http://localhost:3000/` - Splash Page
     - `http://localhost:3000/about` - About Page
     - `http://localhost:3000/gallery` - Gallery Page

3. **Deploy to GitHub**:
   - Push your project to GitHub using the following commands:
     ```bash
     git init
     git add .
     git commit -m "Initial commit for three-page website"
     git remote add origin <your-github-repository-url>
     git push -u origin main
     ```

4. **Submit on Moodle**:
   - Turn in the **GitHub repository link** on Moodle for review.

---

### Evaluation Criteria:

- **Correct Routing**: Each page must be accessible via `/`, `/about`, and `/gallery`.
- **Bootstrap Styling**: Ensure you are using Bootstrap classes to style the elements.
- **Image Usage**: The gallery must contain at least 6 images, and the splash page must include a large background image.
- **Components Are Optional (For Core Requirements)**
- **Bonus (Optional)**:
  - Use the **cowsay** library on the About page.
  - Create custom styles using `.css` files.

---

Good luck, and happy coding!