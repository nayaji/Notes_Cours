# HTML Cheatsheet: Comprehensive Guide

## 1. **HTML Basics**
- **HTML Structure**:
  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
    </head>
    <body>
      <!-- Content here -->
    </body>
  </html>
  ```
- **Common Tags**:
  - `<html>`: Root element.
  - `<head>`: Metadata, links, scripts.
  - `<body>`: Main content.
  - `<title>`: Document title.

---

## 2. **Head Elements**
- **Metadata**:
  ```html
  <meta charset="UTF-8">
  <meta name="description" content="A sample website">
  <meta name="keywords" content="HTML, CSS, JavaScript">
  <meta name="author" content="Your Name">
  ```
- **Links**:
  ```html
  <link rel="stylesheet" href="styles.css">
  <link rel="icon" href="favicon.ico">
  ```
- **Scripts**:
  ```html
  <script src="script.js" defer></script>
  <script>
    console.log("Inline Script");
  </script>
  ```

---

## 3. **Text Elements**
- **Headings**:
  ```html
  <h1>Main Heading</h1>
  <h2>Subheading</h2>
  ```
- **Paragraphs and Spans**:
  ```html
  <p>This is a paragraph.</p>
  <span>This is inline text.</span>
  ```
- **Lists**:
  ```html
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>

  <ol>
    <li>First</li>
    <li>Second</li>
  </ol>
  ```
- **Formatting**:
  ```html
  <strong>Bold Text</strong>
  <em>Italic Text</em>
  <mark>Highlighted Text</mark>
  ```

---

## 4. **Links and Images**
- **Links**:
  ```html
  <a href="https://example.com" target="_blank">Visit Example</a>
  ```
- **Images**:
  ```html
  <img src="image.jpg" alt="Description" width="300" height="200">
  ```
- **Anchor within the Page**:
  ```html
  <a href="#section">Go to Section</a>
  <div id="section">Section Content</div>
  ```

---

## 5. **Forms**
- **Basic Form**:
  ```html
  <form action="/submit" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">

    <label for="email">Email:</label>
    <input type="email" id="email" name="email">

    <input type="submit" value="Submit">
  </form>
  ```
- **Input Types**:
  ```html
  <input type="password" placeholder="Enter password">
  <input type="checkbox" id="agree">
  <input type="radio" name="gender" value="male"> Male
  ```
- **Validation**:
  ```html
  <input type="text" required>
  <input type="number" min="1" max="100">
  ```

---

## 6. **Tables**
- **Basic Table**:
  ```html
  <table border="1">
    <thead>
      <tr>
        <th>Name</th>
        <th>Age</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Alice</td>
        <td>25</td>
      </tr>
      <tr>
        <td>Bob</td>
        <td>30</td>
      </tr>
    </tbody>
  </table>
  ```

---

## 7. **Media**
- **Audio**:
  ```html
  <audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    Your browser does not support audio.
  </audio>
  ```
- **Video**:
  ```html
  <video controls width="400">
    <source src="video.mp4" type="video/mp4">
    Your browser does not support video.
  </video>
  ```

---

## 8. **Semantic HTML**
- **Main Elements**:
  ```html
  <header>Header Content</header>
  <nav>Navigation Links</nav>
  <main>Main Content</main>
  <section>Section Content</section>
  <article>Article Content</article>
  <footer>Footer Content</footer>
  ```

---

## 9. **Miscellaneous**
- **Comments**:
  ```html
  <!-- This is a comment -->
  ```
- **Doctype**:
  ```html
  <!DOCTYPE html>
  ```
- **Character Entities**:
  ```html
  &nbsp; (Space)  &lt; (<)  &gt; (>)  &amp; (&)
  ```
- **Iframes**:
  ```html
  <iframe src="https://example.com" width="600" height="400"></iframe>
  ```

---

## 10. **Best Practices**
- Use semantic tags for better accessibility.
- Optimize images for faster load times.
- Use `alt` attributes for images for accessibility.
- Keep your HTML code clean and indented properly.

---

This cheatsheet provides a detailed overview of HTML fundamentals and advanced features. Use it as a reference while building and structuring web pages!

