# Node.js Cheatsheet: Comprehensive Guide

## 1. **Introduction to Node.js**
- **What is Node.js?**: A runtime environment that allows running JavaScript on the server.
- **Key Features**:
  - Non-blocking I/O.
  - Event-driven architecture.
  - Lightweight and fast.

---

## 2. **Setting Up**
- **Installation**:
  1. Download from [Node.js Official Website](https://nodejs.org/).
  2. Verify installation:
     ```bash
     node -v
     npm -v
     ```
- **Running JavaScript Files**:
  ```bash
  node app.js
  ```

---

## 3. **Core Modules**
### Common Core Modules:
1. **`fs`** (File System):
   ```javascript
   const fs = require('fs');

   // Read file
   fs.readFile('file.txt', 'utf8', (err, data) => {
     if (err) throw err;
     console.log(data);
   });

   // Write file
   fs.writeFile('output.txt', 'Hello, Node.js!', (err) => {
     if (err) throw err;
     console.log('File written!');
   });
   ```

2. **`http`**:
   ```javascript
   const http = require('http');

   const server = http.createServer((req, res) => {
     res.statusCode = 200;
     res.setHeader('Content-Type', 'text/plain');
     res.end('Hello, World!');
   });

   server.listen(3000, () => {
     console.log('Server running at http://localhost:3000/');
   });
   ```

3. **`path`**:
   ```javascript
   const path = require('path');

   const fullPath = path.join(__dirname, 'folder', 'file.txt');
   console.log(fullPath);
   ```

4. **`os`**:
   ```javascript
   const os = require('os');

   console.log('Platform:', os.platform());
   console.log('Free Memory:', os.freemem());
   ```

---

## 4. **npm (Node Package Manager)**
- **Initialize a Project**:
  ```bash
  npm init -y
  ```
- **Install Packages**:
  ```bash
  npm install express
  ```
- **Save as Dev Dependency**:
  ```bash
  npm install nodemon --save-dev
  ```
- **Uninstall Packages**:
  ```bash
  npm uninstall package-name
  ```
- **Global Installation**:
  ```bash
  npm install -g package-name
  ```

---

## 5. **Working with Modules**
- **Creating Modules**:
  ```javascript
  // myModule.js
  const greet = (name) => `Hello, ${name}!`;
  module.exports = greet;

  // app.js
  const greet = require('./myModule');
  console.log(greet('Alice'));
  ```
- **Built-in vs Third-party Modules**:
  - Built-in: `fs`, `http`, `path`.
  - Third-party: Installed via npm, e.g., `express`.

---

## 6. **Asynchronous Programming**
### Callbacks:
```javascript
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

### Promises:
```javascript
fs.promises.readFile('file.txt', 'utf8')
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

### Async/Await:
```javascript
const readFile = async () => {
  try {
    const data = await fs.promises.readFile('file.txt', 'utf8');
    console.log(data);
  } catch (err) {
    console.error(err);
  }
};
readFile();
```

---

## 7. **Express.js Basics**
- **Setup**:
  ```bash
  npm install express
  ```
- **Basic Server**:
  ```javascript
  const express = require('express');
  const app = express();

  app.get('/', (req, res) => {
    res.send('Hello, Express!');
  });

  app.listen(3000, () => {
    console.log('Server running on http://localhost:3000');
  });
  ```
- **Middleware**:
  ```javascript
  app.use(express.json());
  ```

---

## 8. **File System (Advanced)**
- **Stream Files**:
  ```javascript
  const readStream = fs.createReadStream('file.txt', 'utf8');
  readStream.on('data', (chunk) => console.log(chunk));
  ```
- **File Watch**:
  ```javascript
  fs.watch('file.txt', (eventType, filename) => {
    console.log(`File changed: ${filename}`);
  });
  ```

---

## 9. **Debugging**
- **Using Console**:
  ```javascript
  console.log('Debug Info');
  console.error('Error Info');
  ```
- **Debugging with Node.js**:
  ```bash
  node inspect app.js
  ```
  Use browser DevTools or VS Code for breakpoints.

---

## 10. **Deploying Applications**
- **Environment Variables**:
  ```javascript
  require('dotenv').config();
  console.log(process.env.PORT);
  ```
- **Using PM2**:
  ```bash
  npm install pm2 -g
  pm2 start app.js
  ```
- **Deploy to Platforms**:
  - [Heroku](https://www.heroku.com/): `git push heroku main`.
  - [Vercel](https://vercel.com/): `vercel deploy`.

---

## 11. **Best Practices**
- Use `async/await` for cleaner asynchronous code.
- Structure projects into modules (`routes`, `controllers`, `services`).
- Always handle errors (`try/catch`).
- Use `.env` files to store sensitive data.
- Follow security best practices (e.g., `helmet` and `express-validator`).

---

This cheatsheet provides a detailed overview of Node.js, from the basics to advanced topics. Use it to build robust server-side applications efficiently!

