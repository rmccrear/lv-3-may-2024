# Day 2, Hour 1: Getting Started with Framer Motion in Next.js

Welcome to the captivating world of animations with Framer Motion! This hour is dedicated to introducing you to Framer Motion, a popular library for adding animations to React applications. We'll start with the basics, ensuring you grasp why Framer Motion is beneficial and how to incorporate it into your Next.js projects.

## What is Framer Motion?

Framer Motion is a powerful and easy-to-use library for React. It provides a robust set of animation and gesture capabilities, making it simple for developers to add engaging animations to their applications. The beauty of Framer Motion lies in its simplicity and the control it offers over complex animations.

## Installing Framer Motion in Next.js

Before we can start animating, we need to add Framer Motion to our Next.js project. This is easily done with npm or yarn. Open your terminal, navigate to your project directory, and run:

```bash
npm install framer-motion
```

<This is a good time to explore the docs>

This command adds Framer Motion to your project, making its features available for use in your components.

## Creating Simple Animations

With Framer Motion installed, let's create a simple fade-in animation for a welcome message. Framer Motion makes this incredibly straightforward.

### Step 1: Import Framer Motion

First, we import the `motion` component from Framer Motion in our component file. The `motion` component is a special component provided by Framer Motion that can animate any component it wraps.

```jsx
import { motion } from 'framer-motion';
```

### Step 2: Apply a Simple Fade-In Animation

Now, let's use the `motion` component to animate a `<div>` containing a welcome message. We'll make it fade in when the component mounts.

```jsx
function WelcomeMessage() {
  return (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      transition={{ duration: 1 }}
    >
      Welcome to our website!
    </motion.div>
  );
}
```

In this example:

- The `initial` prop defines the starting state of the animation. Here, we start with `opacity: 0` so the element is initially invisible.
- The `animate` prop defines the end state of the animation. We want the element to fully appear, so we set `opacity: 1`.
- The `transition` prop controls how the animation transitions from the initial state to the end state. We've specified a duration of 1 second for the fade-in effect.

And there you have it—a simple yet elegant fade-in animation for a welcome message using Framer Motion in Next.js!

## Conclusion

In this hour, we've introduced Framer Motion and demonstrated how to add it to your Next.js project. We also created a simple fade-in animation as a practical example of what's possible with just a few lines of code. This foundation sets the stage for exploring more complex animations and interactions as we continue our journey with Framer Motion.

<!--! Hour 2 -->

# Day 2, Hour 2: Basic Animations and Transitions with Framer Motion

Building upon our introduction to Framer Motion, this hour focuses on expanding our understanding of basic animations and transitions. We'll explore how to use Framer Motion to animate components in Next.js, making web interfaces more dynamic and engaging.

## Understanding Basic Animations

Framer Motion simplifies the process of animating React components, offering a declarative approach to defining animations. Let's delve deeper into animating components by creating a sliding effect for a sidebar menu.

### Step 1: Set Up Your Component

First, ensure you have Framer Motion installed in your project. Then, prepare a component that you'd like to animate. For this example, we're animating a sidebar:

```jsx
import { motion } from 'framer-motion';

function Sidebar() {
  return <div className="sidebar">{/* Sidebar content here */}</div>;
}
```

### Step 2: Apply a Slide-In Animation

Transform the `<div>` into a `motion.div` and apply the animation properties. We want the sidebar to slide in from the left:

```jsx
<motion.div
  initial={{ x: '-100vw' }} // Start off-screen to the left
  animate={{ x: 0 }} // Animate to its natural position
  transition={{ type: 'spring', stiffness: 100 }} // Use a spring animation for a natural feel
>
  {/* Sidebar content here */}
</motion.div>
```

In this setup, the `initial` and `animate` props define the starting and ending points of the animation, respectively, while the `transition` prop specifies the type of animation. A `spring` animation is used here for a smooth, natural effect as the sidebar comes into view.

## Exploring Transitions

Transitions in Framer Motion allow you to control the timing, duration, and type of animation. They determine how the animation progresses from the initial state to the animate state.

### Adding Hover Effects

Enhance interactivity with simple hover animations. Let's make menu items in our sidebar slightly grow in size when hovered:

```jsx
<motion.div
  whileHover={{ scale: 1.1 }}
  transition={{ type: 'spring', stiffness: 300 }}
>
  Menu Item
</motion.div>
```

The `whileHover` prop defines the animation state when the mouse hovers over the component, creating a responsive feel.

## Practice Exercise: Animate a List

As a practical exercise, animate a list where each item fades and slides into view one after the other. This not only reinforces the concepts we've discussed but also introduces you to sequencing animations in Framer Motion.

```jsx
import { motion } from 'framer-motion';

function AnimatedList({ items }) {
  return (
    <div>
      {items.map((item, index) => (
        <motion.div
          key={item}
          initial={{ opacity: 0, x: -10 }}
          animate={{ opacity: 1, x: 0 }}
          transition={{ delay: index * 0.2 }}
        >
          {item}
        </motion.div>
      ))}
    </div>
  );
}
```

In this example, each item in the list has a slight delay based on its index, creating a staggered animation effect.

## Conclusion

This hour has expanded your toolkit with Framer Motion, demonstrating how to bring components to life with simple yet powerful animations and transitions. By applying these techniques, you can significantly enhance the user experience and interactivity of your Next.js applications.
