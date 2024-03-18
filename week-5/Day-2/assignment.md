# Assignment: Webpack Assignment 2

## Objective

The goal of this assignment is to deepen your understanding of Webpack loaders and plugins. You will configure Webpack to process CSS files using `style-loader` and `css-loader` and then optimize the CSS output for production using the `MiniCssExtractPlugin`.

## Instructions

### Part 1: Project Setup

1. **Initialize Your Project**:

   - If not already done, create a new directory named `webpack-loaders-plugins`.
   - Inside this directory, initialize a new npm project with `npm init -y`.

2. **Install Webpack and Loaders**:

   - Install Webpack, Webpack CLI, `style-loader`, and `css-loader` as development dependencies.

3. **Project Structure**:
   - Create a `src` directory with an `index.js` file and a `styles.css` file inside it.
   - Also, create a `dist` directory and inside it an `index.html` file.

### Part 2: Configure Loaders

1. **Webpack Configuration**:

   - Create a `webpack.config.js` file in your project root.
   - Configure the entry point as `./src/index.js` and the output as `bundle.js` in the `dist` directory.

2. **CSS Loaders**:
   - In your `webpack.config.js`, add a rule to use `style-loader` and `css-loader` for `.css` files.

### Part 3: Implement CSS in Your Application

1. **Adding CSS**:

   - In `src/styles.css`, add some CSS styles of your choice.
   - Import `styles.css` in your `src/index.js` file.

2. **HTML Setup**:
   - Link your bundled JavaScript file in `dist/index.html`.

### Part 4: Install and Configure MiniCssExtractPlugin

1. **Install the Plugin**:

   - Install `mini-css-extract-plugin` as a development dependency.

2. **Plugin Configuration**:
   - Modify your `webpack.config.js` to use `MiniCssExtractPlugin` for extracting CSS into separate files.
   - Replace `style-loader` with `MiniCssExtractPlugin.loader`.

### Part 5: Building for Production

1. **Production Build**:

   - Add a script in your `package.json` to create a production build using Webpack (`"build": "webpack --mode=production"`).
   - Run the build script to generate your production files.

2. **Testing Your Build**:
   - Open `dist/index.html` in a browser to ensure that the external CSS file is loaded and applied correctly.

## Submission

- **GitHub Repository**: Create a repository on GitHub named `webpack-loaders-plugins`. Include your project files, making sure to add a `.gitignore` file to exclude the `node_modules` directory.
- **README.md**: Update the README.md file with instructions on how to run your build script.
- **Submit Your Repository**: Provide the URL to your GitHub repository as your submission.

## Rubric

### Webpack Configuration and Loaders - 5 points

- **Complete (5 pts)**: Correctly configured Webpack with `style-loader` and `css-loader` for CSS files.
- **Partial (3 pts)**: Configuration is mostly correct, but minor issues are present.
- **Limited (1 pt)**: Significant configuration issues or incorrect loader usage.

### CSS Implementation and Style Loading - 5 points

- **Complete (5 pts)**: CSS is correctly implemented and loaded in the web application.
- **Partial (3 pts)**: Minor issues with CSS implementation or loading.
- **Limited (1 pt)**: Major issues with CSS or not loaded correctly.

### MiniCssExtractPlugin Configuration - 5 points

- **Complete (5 pts)**: Correctly configured and used `MiniCssExtractPlugin` to extract CSS into a separate file.
- **Partial (3 pts)**: Plugin is used, but configuration has minor errors.
- **Limited (1 pt)**: Incorrect plugin usage or significant configuration errors.

### Production Build and Optimization - 5 points

- **Complete (5 pts)**: Production build is successfully generated with optimized CSS.
- **Partial (3 pts)**: Build is generated, but optimization could be improved.
- **Limited (1 pt)**: Failed to produce an optimized production build.

### Documentation and Code Quality - 5 points

- **Complete (5 pts)**: Well-documented README with clear instructions. Code is clean and well-organized.
- **Partial (3 pts)**: README lacks some details, or code could be better organized.
- **Limited (1 pt)**: Poor documentation and disorganized code.
