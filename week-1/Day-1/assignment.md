# Hands-On: Clone and Update a Proxy Server

## Objective
Learn how to create and modify a simple proxy server in Node.js using Express and fetch data from an external API while keeping API keys secure. By the end of this exercise, you'll have a customized proxy server that can be used to interact with the Hugging Face API.

## Instructions

### 1. **Clone the Start Code**

- Visit and [fork the starter code](https://dash.deno.com/projects/hard-tuna-21) provided above in a deno sandbox. *Note: this is not forking in GitHub. Click on "Fork to Edit" in Deno. (You will have the option to create your own GitHub repo with this code. However, you will not need to use GitHub for this Hands-On assignment.)*

### 2. **Add Environment Variable**
- Create an access token from huggingface with "Make calls to the serverless Inference API" permissions.
  > **Note:** You must have access to [Mistral Mixtral-8x7B-Instruct-v0.1](https://huggingface.co/mistralai/Mixtral-8x7B-Instruct-v0.1). So make sure to accept the license agreement on the Hugging Face website.
  > Try it out in Postman to make sure it works.
- In your deno playground, add the environment variable `hg_key` under Settings - Environment Variables
- Verify that the route "/caesar-salad" returns a list of ingredients for Caesar Salad.

### 3. **Change Route Name**
- In `server.js`, change the existing route `"/caesar-salad"` to `"/fettuccine-alfredo"`.
- Change the argument to the function fetchIngredientsList, as well.
- Verify that the server responds correctly to requests at this new route.

### 4. **Add a New Route**
- Add a new route called `"/spaghetti-bolognese"`.
- Modify the `fetchIngredientsList` function to accept the new recipe as an argument and return the corresponding data.
- Add your own recipe.

### 5. **Add Your Own Fetch Function**
- Replace the `fetchIngredientsList` function with the fetch function you previously used in your project.
- Add your key
- Ensure that the function can retrieve the relevant data based on the incoming route and user input.

### 6. **BONUS: Update Your Project**
- Update your existing project to use this proxy server.
- Modify your frontend code to fetch data from your proxy server routes instead of directly accessing the Hugging Face API.
- This will help keep your API keys secure.

## Starter Code

You may clone this from https://dash.deno.com/projects/hard-tuna-21 or copy/paste this into a new JS plaground on deno.com

```javascript
// This little JS file runs a server
import express from "npm:express@4.18.2";
const app = express();

// NOTE: Enable CORS for cross-origin requests
// Uncomment these two lines to enable CORS
// import cors from 'npm:cors';
// app.use(cors());

// HELLO WORLD server
app.get("/", (_req, res) => {
  res.send("Welcome to the Dinosaur API!");
});

// PROXY SERVER route for Fettuccine Alfredo
app.get("/fettuccine-alfredo", async (_req, res) => {
  const recipeList = await fetchIngredientsList("Fettuccine Alfredo");
  res.json({ ingredients: recipeList });
});

// NEW ROUTE for Spaghetti Bolognese
app.get("/spaghetti-bolognese", async (_req, res) => {
  const recipeList = await fetchIngredientsList("Spaghetti Bolognese");
  res.json({ ingredients: recipeList });
});

// Start the server
app.listen(3000, () => {
  console.log("Server is running on port 3000");
});

// Function to fetch ingredients from Hugging Face API
async function fetchIngredientsList(userRecipe) {
  const HG_KEY = Deno.env.get("hg_key");
  let url = "https://api-inference.huggingface.co/models/mistralai/Mixtral-8x7B-Instruct-v0.1/v1/chat/completions";
  let payload = {
    model: "mistralai/Mixtral-8x7B-Instruct-v0.1",
    messages: [{ role: "user", content: `List only the individual ingredients in ${userRecipe} by order of importance to the recipe. Omit optional ingredients.` }],
    max_tokens: 500,
    stream: false
  };
  
  let result = await fetch(url, {
    method: "POST",
    body: JSON.stringify(payload),
    headers: {
      "Authorization": `Bearer ${HG_KEY}`,
      "Content-Type": "application/json"
    }
  });

  let data = await result.json();
  if (!(data?.choices?.length > 0)) {
    throw { error: "Error in fetch", result: data };
  } else {
    return data.choices[0].message.content;
  }
};
```

## Expected Output
Upon successful completion, you should have a running proxy server with customized routes that can securely interact with the Hugging Face API without exposing your keys in the client-side code.

## Turn in

Just turn in the link to your playground on deno.

Bonus: Export to GitHub and deploy on deno with a free account.