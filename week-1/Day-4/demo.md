<!--! Hour 1 -->

# Day 4: Publishing to NPM

## Hour 1: Setting Up and Preparing a Package for NPM

### Introduction to NPM Publishing

**Narrative**: "Publishing a package to NPM allows you to share your code with millions of developers worldwide. Today, we'll go through the process of preparing and publishing a simple package."

### Step 1: Setting Up an NPM Account

1. **Create an NPM Account**:
   - Guide the audience to [npmjs.com](https://www.npmjs.com/signup) to sign up for an account.
   - Explain: "An NPM account is required to publish packages. It's a straightforward process on the NPM website."

### Step 2: Initializing a Project for Publishing

1. **Initialize Your Project**:
   - Command: `npm init`
   - Explain: "This command starts the process of creating a `package.json` file for your project. Fill out the prompts to define your package's metadata."

### Step 3: Importance of README.md, Licensing, and Versioning

1. **Creating a README.md File**:
   - Explain: "A `README.md` file is essential for documenting what your package does, how to install it, and how to use it. Good documentation improves your package's usability."
2. **Choosing a License**:
   - Discuss: "Licensing tells others what they can and can't do with your code. A common choice is the MIT license for its permissiveness."
3. **Understanding Versioning**:
   - Explain: "Semantic Versioning (SemVer) is a convention used to manage versions of your package. It helps users understand the impact of updates on their projects."

### Step 4: Creating a Simple Package

1. **Building a `string-utils` Package**:

   - Concept: Introduce a simple utility package that provides basic string manipulation functions.
   - Code Example:

     ```javascript
     // string-utils.js
     function capitalize(str) {
       return str.charAt(0).toUpperCase() + str.slice(1);
     }

     function lowercase(str) {
       return str.toLowerCase();
     }

     module.exports = { capitalize, lowercase };
     ```

   - Explain: "This `string-utils` module includes functions to capitalize and lowercase strings. We'll export these functions so they can be used in other projects."

2. **Understanding `.npmignore`**:
   - Discuss: "The `.npmignore` file works like `.gitignore`, but for NPM. It excludes files from your package, such as tests or documentation, to keep the published package lightweight."

**Wrap-Up**: "We've covered the initial steps to get your project ready for NPM publishing. These foundations—documentation, licensing, versioning, and understanding of `.npmignore`—are crucial for a successful package. Next, we'll go through the process of publishing this package to NPM."

<!--! Hour 2  -->

# Day 4: Publishing to NPM

## Hour 2: Publishing Your Package and Managing Updates

### Publishing to NPM

**Narrative**: "Having prepared our package, it's now time to share it with the world. Publishing to NPM is a simple process but comes with the responsibility of maintaining the package."

### Step 1: Logging into NPM from the CLI

1. **NPM Login**:
   - Command: `npm login`
   - Explain: "This command prompts you for your NPM account credentials, which are required to publish packages. If you're not already logged in, it will authenticate you."

### Step 2: Publishing the Package

1. **Publishing Your Package**:
   - Command: `npm publish`
   - Explain: "Ensure you're in the root directory of your package. This command publishes your package to NPM, making it available for anyone to install. The package name and version from your `package.json` file are used."

### Step 3: Versioning and Updating Your Package

1. **Understanding Semantic Versioning**:

   - Recap: "Semantic Versioning, or SemVer, is a 3-part version number in the format of MAJOR.MINOR.PATCH. Make sure you update these numbers according to the changes in your package."

2. **Updating Your Package**:

   - Command: `npm version patch`
   - Explain: "This command updates the version of your package before publishing an update. Use `patch`, `minor`, or `major` to update the version accordingly based on your changes."

3. **Republishing After an Update**:
   - Command: `npm publish`
   - Note: "After updating the version of your package, you'll need to publish it again for the changes to take effect on NPM."

### Step 4: Post-Publish Considerations

1. **Managing Package Issues and Updates**:

   - Discuss: "Once your package is public, users may report issues or request new features. It's important to actively manage your package by addressing these concerns and publishing updates."

2. **Deprecating Older Versions**:
   - Command: `npm deprecate <package>@<version> "<message>"`
   - Explain: "If you need to deprecate an older version of your package, use this command. It allows you to specify a version and a message for users, guiding them towards updated versions."

**Wrap-Up**: "Publishing a package to NPM is just the beginning. As developers, we have a responsibility to maintain and update our packages. Today, we've learned how to publish, update, and manage an NPM package, equipping you with the knowledge to share your creations with the world responsibly."
