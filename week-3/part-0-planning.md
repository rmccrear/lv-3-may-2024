### Learning Objectives:

By the end of this exercise, you will be able to:
1. Analyze a mockup to identify key components of a webpage.
2. Break down a user interface into reusable components.
3. Map data from a JSON file to the appropriate components in a React project.
4. Plan the structure of a project and document it clearly in a `README.md` file.
5. Begin coding a project by following a structured approach.

---

### Step-by-Step Instructions:

#### Step 1: Examine the Mockup
- Open `mock-up-single-cat.png` and familiarize yourself with the layout.
- Observe the different sections of the page and think about how they relate to each other.

#### Step 2: Define Component Boundaries
- Open the mockup in a drawing program.
- Draw boxes around distinct sections of the mockup. These boxed areas will represent the individual components you'll need to build.

#### Step 3: List the Components
- Make a list of all the components you identified from the mockup.
  - Example: You may need a `CatImage` component to display the cat image and a `CatDetails` component for cat information like name and breed.

#### Step 4: Define the Data for Each Component
- Open the `data/cat-data.json` file and analyze the data structure.
- For each component, identify the specific data it needs from the JSON file.
  - Example: The `CatImage` component will need the image URL, while the `CatDetails` component will need the cat's name and breed.
- Next to each component in your list, write down the data it will receive from `cat-data.json`.

#### Step 5: Document Your Plan
- Create a `README.md` file in your project directory. Or use Canva or excalidraw to document your plan.
- Add your list of components along their data requirements. This will help you stay organized as you proceed.

#### Step 6: Begin Coding
- Start building your components according to the structure you've identified.
- Refer to your mockup and the data file as you write the code. Each component should match a section of the mockup and pull the relevant data from `cat-data.json`.

---

### Summary of What You've Learned:

In this exercise, you learned how to break down a mockup into individual components and structure a React project around them. You practiced identifying the data that each component needs and linked it to a corresponding data source. Additionally, you documented your component structure and data requirements in a `README.md` file, which is an essential part of good development practices. By the end, you applied this structured approach to start coding the components, building a strong foundation for future projects.