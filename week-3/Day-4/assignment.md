# Assignment: Styles Assignment 4

## Objective

Develop a fully functional Recipe Sharing website using Next.js. This assignment will challenge you to apply responsive design techniques with Bootstrap and Tailwind CSS, creating a platform where users can discover and share recipes. You will organize your project within the `src/app` directory, following Next.js best practices, and conclude by deploying your site to Netlify.

## Instructions

### Part 1: Project Setup

1. **Initialize Your Next.js Application**:

   - Start your project using `create-next-app`.

2. **Integrate Bootstrap and Tailwind CSS**:

   - Run `npm install react-bootstrap bootstrap` for React Bootstrap components.
   - Follow the Tailwind CSS setup guide for Next.js projects.

3. **Configure Styles**:
   - Globally import Bootstrap's CSS in `src/app/layout.js`.

### Part 2: Website Development

1. **Navbar Component**:

   - In `src/app/components/Navbar.js`, craft a responsive Navbar using React Bootstrap. It should include navigation links for Home, Categories, Submit Recipe, and About.

2. **Homepage Layout**:

   - Create the Homepage in `src/app/home/page.js` with:
     - A Hero section featuring a large background image, a welcoming headline, and a search bar for recipes.
     - A Featured Recipes section displaying cards for popular recipes.

3. **Categories Page**:

   - Build the Categories page in `src/app/categories/page.js`, listing recipe categories. Use Tailwind CSS for styling cards or list items representing each category.

4. **Submit Recipe Page**:

   - Implement a form in `src/app/submit/page.js` for users to submit their recipes. Utilize Bootstrap for form components and Tailwind CSS for custom styles.

5. **About Page**:
   - The About page in `src/app/about/page.js` should detail the mission of your Recipe Sharing website. Style this page with Tailwind CSS for a clean layout.

### Part 3: Responsive Design

- **Ensure Full Responsiveness**:
  - Use Bootstrap and Tailwind CSS utilities to make your website responsive and accessible across all devices.

### Part 4: Deployment to Netlify

1. **Prepare for Deployment**:

   - Build your project with `npm run build`.

2. **Deploy Your Application**:
   - Deploy your Next.js application using Netlify, linking your project's GitHub repository for continuous deployment.

### Part 5: Documentation

- **Complete README.md**:
  - In your README.md, describe your project, the development process, and any challenges you encountered. Detail how you integrated Bootstrap and Tailwind CSS.
- **Netlify URL**:
  - Include the URL of your deployed website in the README.md.

## Submission

- **GitHub Repository**: Provide the URL of your public GitHub repository containing the project code and README.md.
- **Deployed Website**: Share the Netlify URL of your deployed website.

## Rubric

### Integration and Setup - 5 points

- **Complete (5 pts)**: Perfect setup of Next.js, Bootstrap, and Tailwind CSS. The `src/app` directory structure is correctly implemented.
- **Partial (3 pts)**: Most setup aspects are correct; minor issues do not significantly affect the project.
- **Limited (0 pts)**: Significant setup issues; incorrect or incomplete integration of Bootstrap and/or Tailwind CSS.

### Design and Responsiveness - 5 points

- **Complete (5 pts)**: The website is beautifully designed with full responsiveness. Creative use of Bootstrap and Tailwind CSS enhances aesthetics and user experience.
- **Partial (3 pts)**: Good overall design and responsiveness, with some areas lacking in polish or creativity.
- **Limited (0 pts)**: Poor design; major responsiveness issues. Inadequate use of Bootstrap and Tailwind CSS.

### Content Accuracy and Creativity - 5 points

- **Complete (5 pts)**: Content is engaging, well-organized, and creatively presented. The website accurately reflects the theme of recipe sharing.
- **Partial (3 pts)**: Content is generally relevant and accurate, but presentation could be improved. Some creative elements are present.
- **Limited (0 pts)**: Content lacks relevance or creativity; presentation is poor or inaccurate.

### Functionality and Navigation - 5 points

- **Complete (5 pts)**: All components function as intended with intuitive navigation. Recipe submission and category browsing are seamless.
- **Partial (3 pts)**: Minor functional issues or navigation challenges. Most components work correctly.
- **Limited (0 pts)**: Significant functionality or navigation problems. Key features do not work as expected.

### Deployment and Documentation - 5 points

- **Complete (5 pts)**: Successful deployment on Netlify with comprehensive documentation. Includes a clear project overview, development process, and deployment URL.
- **Partial (3 pts)**: The project is deployed, but documentation is lacking in detail or clarity. Deployment URL is included but may lack context.
- **Limited (0 pts)**: Deployment issues; inadequate documentation. Critical details or deployment URL are missing.
