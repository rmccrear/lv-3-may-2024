Sure! Here's the adjusted rubric that adds up to **100 points**, excluding the bonus points:

### Capstone Project: Web App with API Integration, Authentication, and RESTful Routes

## 100-Point Rubric

1. **Wireframes (10 points)**

   - Create detailed wireframes for the web app, including main components, layout, component hierarchy, and data flow. Incorporate these into planning and StoryBook stories.

2. **README (10 points)**

   - Create a `README.md` that provides a clear description of the project, instructions on how to run it, and testing guidelines. Ensure it is well-structured, as it represents the first impression of your project.

3. **Pages (10 points)**

   - Create at least 3 pages: a home page, an API integration page, and an about page. Additional pages are optional but encouraged.

4. **Components (10 points)**

   - Create at least 5 components for your web app. Ensure components are reusable and logically structured.

5. **Component Testing (5 points)**

   - Use StoryBook to test at least 3 components.

6. **Design (10 points)**

   - Use Tailwind CSS for styling. Thoughtfully design the user interface.

7. **API Integration (10 points)**

   - Integrate an API into your project that requires an API key hidden behind an API proxy. Create at least 2 routes in the `/api` folder in your Next.js project.

8. **Services (10 points)**

   - Include at least one service that fetches data from the API and passes it to components. Implement functionality to send an email upon form submission.

9. **Environment Variables (5 points)**

   - Use a `.env.local` file to store sensitive information such as API keys. Create a `.env.local.example` file to indicate required keys without exposing sensitive data.

10. **Persistent Data (10 points)**

    - Use a database, such as upstash with Vercel, to persist user data, such as favorites, likes, or comments. Data should be collected from the user and stored securely.

11. **Deployment (10 points)**

    - Deploy your web app to a hosting platform such as Vercel or Netlify. Ensure the deployment is successful and the app is accessible online.

### Optional Bonus Points (Not included in total)

1. **Authentication (5 points - Optional)**
   - Implement Magic Link email authentication in the project.

2. **RESTful Routes (10 points - Optional)**
   - Implement RESTful routes that cover CRUD operations (Create, Read, Update, Delete). At a minimum, implement Create and Read, with additional routes for Update and Delete if time permits.

### Total: 100 points