## Assignment: Node Assignment 4

### Objective

Create and publish a simple utility package to NPM that offers array manipulation functions. This package should demonstrate your understanding of setting up a package for NPM, including writing a useful README, choosing an appropriate license, understanding semantic versioning, and utilizing `.npmignore`.

### Instructions

#### Step 1: Initialize Your Package

- **Setup**: Initialize a new Node.js project in a clean directory. Use `npm init` to create a `package.json` file, filling in details like name, version, and entry point (e.g., `index.js`).

#### Step 2: Create Your Utility Functions

- **Develop Array Utilities**:
  - In your project, create an `index.js` file.
  - Implement at least two array utility functions, such as `removeDuplicates(arr)` and `mergeArrays(arr1, arr2)`. These functions should perform actions indicated by their names and be exported from `index.js`.

#### Step 3: Prepare for Publishing

- **Documentation**: Write a `README.md` file explaining what your package does, how to install it, and how to use the array utilities.
- **License**: Choose an appropriate license for your package (e.g., MIT) and include it in your package as a `LICENSE.txt` file.

- **Versioning**: Ensure your package version follows Semantic Versioning (SemVer).

- **`.npmignore`**: Create a `.npmignore` file to exclude unnecessary files (e.g., test files, documentation) from the published package.

#### Step 4: Publish Your Package

- **NPM Login**: Use `npm login` to log in to your NPM account from the command line.

- **Publish**: Run `npm publish` to publish your package to NPM. Make sure your package name is unique.

### Rubric

#### Utility Function Implementation - 5 points

- Complete (5 pts): Implements at least two array utility functions that work as expected.
- Partial (3 pts): Implements one function correctly, or functions have minor bugs.
- Limited (0 pts): Functions are not implemented correctly or do not perform as intended.

#### Documentation (README.md and LICENSE) - 5 points

- Complete (5 pts): `README.md` clearly documents the package's purpose, installation, and usage. An appropriate license file is included.
- Partial (3 pts): `README.md` or license file is missing essential information or clarity.
- Limited (0 pts): Lacks `README.md`, license file, or both.

#### Semantic Versioning - 5 points

- Complete (5 pts): Correctly applies Semantic Versioning to the package version.
- Partial (3 pts): Attempts to follow SemVer but with minor errors in versioning logic.
- Limited (0 pts): Does not apply Semantic Versioning principles.

#### `.npmignore` Usage - 5 points

- Complete (5 pts): Effectively uses `.npmignore` to exclude unnecessary files from the package.
- Partial (3 pts): `.npmignore` is present but does not correctly exclude all unnecessary files.
- Limited (0 pts): Fails to include `.npmignore` or incorrectly configured, leading to bloated package.

#### NPM Publishing - 5 points

- Complete (5 pts): Successfully publishes the package to NPM, accessible for installation.
- Partial (3 pts): Publishes the package, but with issues in package visibility or installability.
- Limited (0 pts): Fails to publish the package to NPM or does not complete the publishing process.
