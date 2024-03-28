# Day 1: Splash Page Components and Setup

The journey begins with setting up the foundational components for our Community Market App's splash page. This initial phase involves the creation of a visually appealing and informative landing page, incorporating local news, navigation, and sponsors, establishing a community-centric marketplace.

## Part 1: Project Overview and Initial Planning

### Objectives and Splash Page Features

- Introduce the Community Market App, emphasizing the marketplace's community focus.
- Outline the splash page features: local news highlights, navigation to different sections, and sponsor showcases.

### Designing the Splash Page

- Utilize tools like Figma or Sketch to draft the splash page design, incorporating elements for the local news feed, navigation bar, and sponsors.
- Ensure the design is responsive, leveraging Bootstrap components for consistency and speed.

## Part 2: Setting Up the Environment and Tools

### Next.js and Bootstrap Integration

```
npx create-next-app@latest community-market-app
cd community-market-app
npm install react-bootstrap bootstrap axios
```

- Update `README.md` with the project's description, including new splash page features.
- Ensure Bootstrap CSS is included in your project by modifying `_app.js`:

```
import 'bootstrap/dist/css/bootstrap.min.css';
```

### Structuring the Project

- Discuss the project structure, emphasizing the separation of components (`components` directory), pages (`pages` directory), and utilities (`utils` directory).
- Stress the importance of consistent naming conventions and organization for scalability.

## Part 3: Developing the Splash Page Components

### Local News Component

- Detail the setup for the `LocalNews` component, utilizing `axios` for asynchronous data fetching from the News API, and managing state with React's `useState` and `useEffect`.
- Implement error handling for API requests and discuss optimizing the user experience by handling loading states.

### Navigation Bar

- Introduce the `NavArea` component, utilizing React Bootstrap for a responsive navigation bar. Discuss customization options to fit the app's theme and user navigation requirements.

### Sponsors Display

- Explain the implementation of the `Sponsors` component, showcasing sponsor information with images. Highlight the use of the `Image` component from `next/image` for optimized image handling.

### Environment Variables for Security

- Guide on using environment variables for storing sensitive information like the News API key:

```
touch .env.local
echo "NEXT_PUBLIC_NEWS_API_KEY=your_api_key_here" > .env.local
```

- Update the data fetching in `LocalNews` to utilize `process.env.NEXT_PUBLIC_NEWS_API_KEY`.

## Part 4: Integrating and Testing Components

### Assembling Components on the Splash Page

- Ensure the `LocalNews`, `NavArea`, and `Sponsors` components are correctly integrated into the splash page, creating a cohesive and functional layout.

```js
import React, { useEffect, useState } from 'react';
import axios from 'axios';
import NewsCard from './NewsCard'; // Ensure the path is correct

export default function LocalNews() {
  const [news, setNews] = useState([]);

  useEffect(() => {
    async function fetchNews() {
      try {
        const response = await axios.get(
          'https://gnews.io/api/v4/search?q=pittsburgh&category=general&apikey=80509269cd1bb9e61e52877670327c69&lang=en',
        );
        setNews(response.data.articles);
      } catch (error) {
        console.log(error);
      }
    }
    fetchNews();
  }, []);

  return (
    <section className="p-4">
      <h2 className="d-flex justify-content-center">In the Know: Local News</h2>
      <div className="d-flex gap-5 flex-wrap">
        {news.map((article, index) => (
          <NewsCard
            key={index}
            article={article}
          />
        ))}
      </div>
    </section>
  );
}
```

```js
import Container from 'react-bootstrap/Container';
import Nav from 'react-bootstrap/Nav';
import Navbar from 'react-bootstrap/Navbar';
import NavDropdown from 'react-bootstrap/NavDropdown';

const NavArea = () => {
  return (
    <>
      <Navbar
        expand="lg"
        className="bg-body-tertiary"
      >
        <Container>
          <Navbar.Brand href="#home">React-Bootstrap</Navbar.Brand>
          <Navbar.Toggle aria-controls="basic-navbar-nav" />
          <Navbar.Collapse id="basic-navbar-nav">
            <Nav className="me-auto">
              <Nav.Link href="#home">Home</Nav.Link>
              <Nav.Link href="#link">Community</Nav.Link>
            </Nav>
          </Navbar.Collapse>
        </Container>
      </Navbar>
    </>
  );
};

export default NavArea;
```

```js
import React from 'react';
import Card from 'react-bootstrap/Card';
import Button from 'react-bootstrap/Button';

const NewsCard = ({ article }) => {
  return (
    <Card
      className="mb-4 shadow-lg mx-auto"
      style={{ width: '380px' }}
    >
      <Card.Img
        variant="top"
        src={article.image}
        alt="News Image"
        className="h-48 w-full object-cover"
      />
      <Card.Body>
        <Card.Title className="font-bold">{article.title}</Card.Title>
        <Card.Text className="text-sm">{article.description}</Card.Text>
        <Button
          variant="primary"
          href={article.url}
          target="_blank"
          className="mt-2"
        >
          Read More
        </Button>
      </Card.Body>
    </Card>
  );
};

export default NewsCard;
```

```js
import Image from 'next/image';

const Sponsors = () => {
  const sponsors = [
    {
      name: 'Airport Express',
      description: 'Fast and reliable airport shuttle services.',
      contact: 'Call us at 123-456-7890',
      src: 'airport',
    },
    {
      name: 'EcoRive Cleaners',
      description:
        'Eco-friendly car cleaning services for your cars and trucks.',
      contact: 'Email us at contact@ecorive.com',
      src: 'ecorive',
    },
    {
      name: 'GrassRoots Landscaping',
      description: 'Innovative landscaping solutions for modern homes.',
      contact: 'Visit us at 123 Greenway Blvd, Nature City',
      src: 'grass',
    },
    {
      name: 'GreenLeaf Grocers',
      description: 'Fresh organic groceries right to your doorstep.',
      contact: 'Order online at greenleafgrocers.com',
      src: 'greenleaf',
    },
    {
      name: 'LegalEase Consultancy',
      description: 'Expert legal advice for personal and business needs.',
      contact: 'Schedule a consultation at legalease.com',
      src: 'legal',
    },
    {
      name: 'Mechano Auto Repairs',
      description: 'Trusted car repair and maintenance services.',
      contact: 'Book an appointment at 456-789-0123',
      src: 'mechanic',
    },
    {
      name: 'Pasta Panorama',
      description: 'Delicious homemade pasta and Italian cuisine.',
      contact: 'Reserve a table at pastapanorama.com',
      src: 'pasta',
    },
    {
      name: 'Seafood Delight',
      description: 'The freshest seafood in town, from our shore to your door.',
      contact: 'Order now at 789-012-3456',
      src: 'seafood',
    },
    {
      name: 'Sunset Photography',
      description: 'Capturing your special moments against stunning sunsets.',
      contact: 'Inquire at sunsetphoto.com',
      src: 'sunset',
    },
  ];

  return (
    <section>
      <h2 className="d-flex justify-content-center">Meet Our Sponsors</h2>
      <div className="d-flex flex-wrap justify-center gap-4 p-5">
        {sponsors.map((sponsor, index) => (
          <div
            key={index}
            className="text-center"
          >
            <Image
              width={150}
              height={150}
              src={`/sponsors/${sponsor.src}.png`}
              alt={`${sponsor.name} Logo`}
              className="rounded-lg shadow-lg"
            />
            <h3 className="mt-2">{sponsor.name}</h3>
            <p>{sponsor.description}</p>
            <p className="font-bold">{sponsor.contact}</p>
          </div>
        ))}
      </div>
    </section>
  );
};

export default Sponsors;
```

```js
import React from 'react';

const styles = {
  container: {
    display: 'flex',
    flexDirection: 'column',
    alignItems: 'center',
    justifyContent: 'center',
    padding: '20px',
    backgroundColor: '#f5f5f5',
    borderRadius: '8px',
    boxShadow: '0 2px 4px rgba(0,0,0,0.1)',
    margin: '20px',
    textAlign: 'center',
  },
  header: {
    fontSize: '24px',
    margin: '10px 0',
  },
  text: {
    fontSize: '16px',
    margin: '10px 0',
  },
  button: {
    padding: '10px 20px',
    fontSize: '18px',
    color: '#fff',
    backgroundColor: '#007bff',
    border: 'none',
    borderRadius: '5px',
    cursor: 'pointer',
    marginTop: '20px',
  },
};

// The WelcomeBanner component
const WelcomeBanner = () => {
  return (
    <div style={styles.container}>
      <h2 style={styles.header}>Welcome to Our Community Marketplace!</h2>
      <p style={styles.text}>
        Our platform is designed to bring the community together by allowing you
        to easily buy and sell items. Whether you're looking to declutter your
        home or find treasures, our marketplace is here for you.
      </p>
      <p style={styles.text}>
        Why wait? Join us now and start sharing your items with your neighbors.
        It's easy, fast, and convenient.
      </p>
      <button style={styles.button}>Sell Your Stuff</button>
    </div>
  );
};

export default WelcomeBanner;
```

### Testing Functionality and Responsiveness

- Conduct thorough testing across different devices and browsers to ensure the splash page is responsive and the components function as intended.

### Debugging and Refinement

- Debug any issues discovered during testing, focusing on performance optimizations and user experience enhancements.

## Conclusion

At the end of Day 1, students will have a fully functional splash page for the Community Market App, featuring local news, navigation, and sponsors. This page not only serves as the welcoming face of the app but also sets the stage for further development of marketplace functionalities.

This solid foundation prepares students for the exciting development journey ahead, where we will expand the app's capabilities to include core marketplace features.
