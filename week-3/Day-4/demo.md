# Day 4, Hour 1: Project Kickoff and Initial Setup for a Responsive Website

Welcome to Day 4, where we embark on creating a Pet Adoption website. This project will allow us to apply our knowledge of integrating Bootstrap and Tailwind CSS within a Next.js framework to build a responsive and visually appealing website. We'll start by setting up our project structure, focusing on incorporating Bootstrap and Tailwind CSS for our navbar and homepage layout.

## Introduction to the Pet Adoption Website Project

Our goal is to develop a user-friendly Pet Adoption website. This site will showcase pets available for adoption, providing a seamless and accessible platform for prospective pet owners to find their new companions.

## Setting Up the Project Structure

A well-organized project structure is crucial for development efficiency and maintainability. In Next.js, the `src/app/` directory plays a central role in structuring our application.

### Integrating Bootstrap and Tailwind CSS

After initializing your Next.js project, the next step is to integrate Bootstrap and Tailwind CSS. These frameworks will aid in developing a responsive layout and ensure design consistency.

1. **Install Bootstrap and React Bootstrap**:

   ```bash
   npm install react-bootstrap bootstrap
   ```

2. **Setting Up Tailwind CSS**:

   Tailwind CSS can be included during your project's initial setup if selected from Next.js setup prompts. For manual setup, follow the Tailwind CSS documentation.

3. **Global Imports**:

   Import Bootstrap's CSS globally in your `src/app/layout.js` or a similar file to apply Bootstrap's styles across your application.

   ```jsx
   // src/app/layout.js
   import 'bootstrap/dist/css/bootstrap.min.css';
   ```

## Building the Navbar and Homepage Layout

With our project structured and styling frameworks in place, let's proceed to build out the navbar and homepage layout.

### Creating a Responsive Navbar

In `src/app/components/Navbar.js`, utilize React Bootstrap to create a navigation bar:

```jsx
import { Navbar, Nav } from 'react-bootstrap';

const NavigationBar = () => {
  return (
    <Navbar bg="light" expand="lg">
      <Navbar.Brand href="/">Pet Adoption</Navbar.Brand>
      <Nav className="ml-auto">
        <Nav.Link href="/adopt">Adopt</Nav.Link>
        <Nav.Link href="/about">About Us</Nav.Link>
      </Nav>
    </Navbar>
  );
};

export default NavigationBar;
```

### Implementing the Homepage Layout

Next, let's add the Navbar to our homepage layout in `src/app/page.js`, demonstrating the basic setup for a page in our application:

```jsx
import NavigationBar from './components/Navbar';
// Other imports as necessary

export default function HomePage() {
  return (
    <div>
      <NavigationBar />
      {/* Further homepage content */}
    </div>
  );
}
```

## Conclusion

We've successfully kicked off our Pet Adoption website project, integrating Bootstrap and Tailwind CSS into our Next.js setup. Starting with the navbar and homepage layout, we're laying the foundation for a responsive and accessible web application. This initial setup paves the way for adding more detailed components and features as we progress.

<!--! Hour 2 -->

# Day 4, Hour 1: Project Kickoff and Initial Setup for a Responsive Website

Welcome to Day 4, where we embark on creating a Pet Adoption website. This project will allow us to apply our knowledge of integrating Bootstrap and Tailwind CSS within a Next.js framework to build a responsive and visually appealing website. We'll start by setting up our project structure, focusing on incorporating Bootstrap and Tailwind CSS for our navbar and homepage layout.

## Introduction to the Pet Adoption Website Project

Our goal is to develop a user-friendly Pet Adoption website. This site will showcase pets available for adoption, providing a seamless and accessible platform for prospective pet owners to find their new companions.

## Setting Up the Project Structure

A well-organized project structure is crucial for development efficiency and maintainability. In Next.js, the `src/app/` directory plays a central role in structuring our application.

### Integrating Bootstrap and Tailwind CSS

After initializing your Next.js project, the next step is to integrate Bootstrap and Tailwind CSS. These frameworks will aid in developing a responsive layout and ensure design consistency.

1. **Install Bootstrap and React Bootstrap**:

   ```bash
   npm install react-bootstrap bootstrap
   ```

2. **Setting Up Tailwind CSS**:

   Tailwind CSS can be included during your project's initial setup if selected from Next.js setup prompts. For manual setup, follow the Tailwind CSS documentation.

3. **Global Imports**:

   Import Bootstrap's CSS globally in your `src/app/layout.js` or a similar file to apply Bootstrap's styles across your application.

   ```jsx
   // src/app/layout.js
   import 'bootstrap/dist/css/bootstrap.min.css';
   ```

## Building the Navbar and Homepage Layout

With our project structured and styling frameworks in place, let's proceed to build out the navbar and homepage layout.

### Creating a Responsive Navbar

In `src/app/components/Navbar.js`, utilize React Bootstrap to create a navigation bar:

```jsx
import { Navbar, Nav } from 'react-bootstrap';

const NavigationBar = () => {
  return (
    <Navbar bg="light" expand="lg">
      <Navbar.Brand href="/">Pet Adoption</Navbar.Brand>
      <Nav className="ml-auto">
        <Nav.Link href="/adopt">Adopt</Nav.Link>
        <Nav.Link href="/about">About Us</Nav.Link>
      </Nav>
    </Navbar>
  );
};

export default NavigationBar;
```

### Implementing the Homepage Layout

Next, let's add the Navbar to our homepage layout in `src/app/page.js`, demonstrating the basic setup for a page in our application:

```jsx
import NavigationBar from './components/Navbar';
// Other imports as necessary

export default function HomePage() {
  return (
    <div>
      <NavigationBar />
      {/* Further homepage content */}
    </div>
  );
}
```

## Conclusion

We've successfully kicked off our Pet Adoption website project, integrating Bootstrap and Tailwind CSS into our Next.js setup. Starting with the navbar and homepage layout, we're laying the foundation for a responsive and accessible web application. This initial setup paves the way for adding more detailed components and features as we progress.

<!--! Hour 2 -->

# Day 4, Hour 2: Completing Core Components

Building upon our initial setup, this hour is dedicated to enhancing our Pet Adoption website by completing core components of the homepage. We'll focus on adding responsive features to ensure accessibility and utilizing Bootstrap and Tailwind CSS to maintain design consistency. Let's dive into creating additional pages such as "About Us" and "Contact" to enrich our site's content.

## Adding Responsive Features with Bootstrap and Tailwind CSS

Responsive design is crucial for ensuring your website is accessible and user-friendly across all devices. Bootstrap and Tailwind CSS both offer utilities to help us achieve this with minimal effort.

### Example: Using Bootstrap for a Responsive Navbar

Bootstrap's navbar component automatically includes responsive features. Here's a reminder on how to implement it in `src/app/components/Navbar.js`:

```jsx
import { Navbar, Nav } from 'react-bootstrap';

const NavigationBar = () => {
  return (
    <Navbar bg="light" expand="lg" collapseOnSelect>
      <Navbar.Brand href="/">Pet Adoption</Navbar.Brand>
      <Navbar.Toggle aria-controls="basic-navbar-nav" />
      <Navbar.Collapse id="basic-navbar-nav">
        <Nav className="ml-auto">
          <Nav.Link href="/adopt">Adopt</Nav.Link>
          <Nav.Link href="/about">About Us</Nav.Link>
        </Nav>
      </Navbar.Collapse>
    </Navbar>
  );
};
```

### Example: Tailwind CSS for a Responsive Layout

Tailwind CSS provides utility classes that make building responsive layouts straightforward. For instance, to adjust the layout of your homepage based on screen size, you can use the following in `src/app/page.js`:

```jsx
<div className="container mx-auto px-4">
  {/* Content here will be centered and responsive */}
</div>
```

## Creating Additional Pages

Expanding our website, let's add an "About Us" and "Contact" page. These pages will help visitors learn more about the mission behind the Pet Adoption site and how to get in touch.

### About Us Page

Create a new folder and page file for the About Us section, following the Next.js file-based routing in `src/app/about/page.js`:

```jsx
// src/app/about/page.js
import NavigationBar from '../components/Navbar';

export default function AboutPage() {
  return (
    <div>
      <NavigationBar />
      <main className="container mx-auto px-4">
        <h1>About Us</h1>
        <p>This is what we do and why we do it.</p>
      </main>
    </div>
  );
}
```

### Contact Page

Similarly, for the Contact page in `src/app/contact/page.js`:

```jsx
// src/app/contact/page.js
import NavigationBar from '../components/Navbar';

export default function ContactPage() {
  return (
    <div>
      <NavigationBar />
      <main className="container mx-auto px-4">
        <h1>Contact Us</h1>
        <p>How to reach us...</p>
      </main>
    </div>
  );
}
```

## Conclusion

In this hour, we've taken significant steps in building our Pet Adoption website by completing core components and ensuring our site is responsive and accessible. By utilizing Bootstrap for components like the navbar and Tailwind CSS for layout responsiveness, we've laid a solid foundation for a professional, user-friendly website.

