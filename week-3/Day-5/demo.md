# Day 5, Hour 1: Review and Practice by Building a Sweets Storefront Website

Today, we embark on a comprehensive review session by building a Sweets Storefront Website from scratch. This practical exercise will encompass the core concepts we've discussed throughout the week, including Sass, CSS Modules, React Bootstrap, and Tailwind CSS. The goal is to demonstrate how to approach a project integrating these technologies in a Next.js environment, providing a clear example for you to follow and learn from.

## Project Overview

The "Sweets Storefront" website will feature three main pages:

1. **Home Page**: Highlighting featured sweets and the brand's story.
2. **Products Page**: Showcasing a gallery of candies and cookies.
3. **Contact Page**: Offering details on how to visit or get in touch with the store.

## Initial Setup

Before we start coding, ensure your Next.js project is set up to support both Bootstrap and Tailwind CSS. For this session, we'll assume Tailwind CSS is already configured through the Next.js setup process, and we'll focus on incorporating React Bootstrap.

### Integrating React Bootstrap

```bash
npm install react-bootstrap bootstrap
```

After installation, import Bootstrap's CSS in your global styles file (`src/app/global.css`):

```css
@import '~bootstrap/dist/css/bootstrap.min.css';
```

## Building the Home Page

Let's begin with the Home Page, leveraging React Bootstrap for the navigation bar and Tailwind CSS for custom styling elements like the featured sweets section.

### Navigation Bar

Create a `NavigationBar` component in `src/app/components/NavigationBar.js`:

```jsx
import { Navbar, Nav } from 'react-bootstrap';

export default function NavigationBar() {
  return (
    <Navbar bg="light" expand="lg">
      <Navbar.Brand href="/">Sweets Storefront</Navbar.Brand>
      <Nav className="ml-auto">
        <Nav.Link href="/products">Products</Nav.Link>
        <Nav.Link href="/contact">Contact</Nav.Link>
      </Nav>
    </Navbar>
  );
}
```

### Featured Sweets Section

In `src/app/page.js`, introduce a section for featured sweets, applying Tailwind CSS for styling:

```jsx
import NavigationBar from './components/NavigationBar';

export default function HomePage() {
  return (
    <div className="container mx-auto p-4">
      <NavigationBar />
      <div className="mt-8">
        <h2 className="text-2xl font-bold">Featured Sweets</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
          {/* Dynamic list of featured sweets */}
        </div>
      </div>
    </div>
  );
}
```

## Products and Contact Pages

Repeat a similar process for the Products and Contact pages, creating separate components for each section and utilizing both React Bootstrap and Tailwind CSS for layout and styling. Ensure your components are placed appropriately within the `src/app/` directory, following the Next.js routing conventions.

## Review and Key Takeaways

- **Project Structure**: Organize your project files within the `src/app/` directory, utilizing a modular approach for components and styles.
- **Styling with Bootstrap and Tailwind CSS**: Leverage the strengths of both Bootstrap (for component structure) and Tailwind CSS (for custom styling and responsiveness).
- **Responsive Design**: Use utility classes from both styling frameworks to ensure your website is responsive and accessible across different devices.

This hands-on buildout serves as a practical review of integrating styling frameworks within a Next.js project, reinforcing the concepts covered throughout the week. By walking through the development of the Sweets Storefront Website, you gain a clearer understanding of how to apply these technologies in your future projects.

<!--! Hour 2  -->

# Day 5, Hour 2: Completing the Sweets Storefront Website

In this hour, we'll focus on finalizing our Sweets Storefront Website, adding the finishing touches to ensure a fully functional, responsive, and visually appealing site. We'll complete the Products and Contact pages, integrate responsive design features, and discuss how to maintain consistency across the site using React Bootstrap and Tailwind CSS.

## Completing the Products Page

The Products Page will showcase the sweets available in the storefront. We'll use a combination of React Bootstrap for the layout and Tailwind CSS for custom styling.

### Step 1: Layout with React Bootstrap

In `src/app/products/page.js`, create a grid layout to display product cards. Each card will use Bootstrap's Card component for consistency.

```jsx
import { Card, Button } from 'react-bootstrap';
import NavigationBar from '../components/NavigationBar';

const products = [
  {
    id: 1,
    name: 'Candy',
    description: 'Sweet and colorful.',
    imageUrl: '/candy.jpg',
  },
  // Add more products as needed
];

export default function ProductsPage() {
  return (
    <div className="container mx-auto p-4">
      <NavigationBar />
      <h1 className="text-2xl font-bold my-4">Our Products</h1>
      <div className="grid md:grid-cols-3 gap-4">
        {products.map((product) => (
          <Card key={product.id} className="h-100">
            <Card.Img variant="top" src={product.imageUrl} />
            <Card.Body>
              <Card.Title>{product.name}</Card.Title>
              <Card.Text>{product.description}</Card.Text>
              <Button variant="primary">Learn More</Button>
            </Card.Body>
          </Card>
        ))}
      </div>
    </div>
  );
}
```

### Step 2: Custom Styling with Tailwind CSS

Utilize Tailwind CSS to enhance the visual appeal and responsiveness of the Products Page. Tailwind's utility classes can be applied directly to React Bootstrap components for custom spacing, typography, and layout adjustments.

## Building the Contact Page

The Contact Page provides visitors with information on how to reach the storefront. This page will include a simple contact form and store information.

### Implementing the Contact Form

For the form layout, you can use React Bootstrap's Form components for structure and Tailwind CSS for styling.

In `src/app/contact/page.js`:

```jsx
import { Form, Button } from 'react-bootstrap';
import NavigationBar from '../components/NavigationBar';

export default function ContactPage() {
  return (
    <div className="container mx-auto p-4">
      <NavigationBar />
      <h1 className="text-2xl font-bold my-4">Contact Us</h1>
      <Form>
        <Form.Group controlId="formBasicEmail">
          <Form.Label>Email address</Form.Label>
          <Form.Control type="email" placeholder="Enter email" />
        </Form.Group>
        <Form.Group controlId="formBasicMessage">
          <Form.Label>Message</Form.Label>
          <Form.Control as="textarea" rows={3} />
        </Form.Group>
        <Button variant="primary" type="submit">
          Submit
        </Button>
      </Form>
    </div>
  );
}
```

## Ensuring Site-wide Consistency and Responsiveness

- **Consistency**: Use React Bootstrap components as the foundation for your site's layout and interface elements, ensuring a consistent look and feel.
- **Responsiveness**: Apply Tailwind CSS utility classes to fine-tune and enhance the responsiveness of your site. Ensure that your layout, typography, and interactive elements adapt gracefully across devices.

## Conclusion

By completing the Products and Contact pages, we've brought our Sweets Storefront Website to life. This session not only solidified our understanding of integrating React Bootstrap and Tailwind CSS in a Next.js project but also demonstrated practical approaches to building responsive and user-friendly web experiences. As we move into the final hour of practice and Q&A, remember that the skills you've developed this week are foundational to becoming a proficient web developer in today's dynamic tech landscape.
