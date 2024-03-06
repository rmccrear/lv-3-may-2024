## Optional Stretch Assignment: Building a Web Scraper with Node.js

### Objective

Your goal is to build a command-line web scraper that utilizes `axios` for fetching web pages and `cheerio` for parsing and extracting elements from the HTML. This project will consolidate your understanding of Node.js, npm packages, and the practical application of modules in a complex scenario.

### Instructions

#### Preparation

- Ensure Node.js and npm are installed on your system.
- Create a new directory for your project and navigate into it.
- Initialize a new Node.js project with `npm init -y`.
- Install `axios` and `cheerio` using npm (`npm install axios cheerio`).

#### Development

1. **Setup Your Scraper**:

   - In your project directory, create a file named `scraper.js`.
   - Import `axios` and `cheerio` at the top of your file.

2. **Fetching Web Content**:

   - Use `axios` to fetch the HTML content of a website of your choice (ensure it's legal and ethical to scrape it).
   - Load the fetched HTML content into `cheerio` to prepare for parsing.

3. **Parsing HTML with Cheerio**:

   - Choose specific data to extract from the page. This could be things like article titles, links, or any other information relevant to the site you've chosen.
   - Utilize `cheerio`'s jQuery-like selectors to find and extract the data from the HTML structure.

4. **Organizing Extracted Data**:

   - Structure the extracted data in a meaningful way, potentially as an array of objects.
   - Log the structured data to the console, or for an added challenge, write the data to a JSON file using Node's `fs` module.

5. **Error Handling**:
   - Implement basic error handling for your HTTP requests and parsing logic to manage any potential failures gracefully.

#### Stretch Challenges

- **Pagination Handling**: If the site has pagination, implement logic in your scraper to navigate through multiple pages and aggregate data from each page.
- **Dynamic Content**: Experiment with scraping sites that load data dynamically with JavaScript. Note: This might require additional tools beyond `axios` and `cheerio` and can be significantly more challenging.

### Note

This assignment is a stretch goal and is intended for optional practice. It is not required and will not be submitted or graded. Please ensure to respect the website's `robots.txt` and terms of service when choosing a site to scrape.
