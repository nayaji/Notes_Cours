# JavaScript Cheatsheet: Backend Guide

## 1. **Setting Up Node.js**
- **Initialize Project**:
  ```bash
  npm init -y
  ```
- **Installing Packages**:
  ```bash
  npm install express mongoose dotenv
  ```
- **Running a Script**:
  ```bash
  node app.js
  ```

---

## 2. **Core Modules**
- **File System (fs)**:
  ```javascript
  const fs = require("fs");

  // Reading a file
  fs.readFile("file.txt", "utf-8", (err, data) => {
    if (err) throw err;
    console.log(data);
  });

  // Writing to a file
  fs.writeFile("file.txt", "Hello, World!", (err) => {
    if (err) throw err;
    console.log("File written successfully");
  });
  ```
- **Path**:
  ```javascript
  const path = require("path");

  const filePath = path.join(__dirname, "folder", "file.txt");
  console.log(filePath);
  ```
- **HTTP**:
  ```javascript
  const http = require("http");

  const server = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader("Content-Type", "text/plain");
    res.end("Hello, World!\n");
  });

  server.listen(3000, () => {
    console.log("Server running at http://localhost:3000/");
  });
  ```

---

## 3. **Express.js**
- **Setting Up**:
  ```javascript
  const express = require("express");
  const app = express();

  app.use(express.json()); // Parse JSON body

  app.get("/", (req, res) => {
    res.send("Hello, World!");
  });

  app.listen(3000, () => {
    console.log("Server running on port 3000");
  });
  ```
- **Routes**:
  ```javascript
  app.post("/data", (req, res) => {
    res.json({ message: "Data received", data: req.body });
  });

  app.put("/update", (req, res) => {
    res.send("Data updated");
  });

  app.delete("/delete", (req, res) => {
    res.send("Data deleted");
  });
  ```

---

## 4. **Middleware**
- **Using Middleware**:
  ```javascript
  app.use((req, res, next) => {
    console.log(`${req.method} ${req.url}`);
    next();
  });
  ```
- **Error Handling Middleware**:
  ```javascript
  app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send("Something went wrong!");
  });
  ```

---

## 5. **Database Integration (MongoDB)**
- **Connecting to MongoDB**:
  ```javascript
  const mongoose = require("mongoose");

  mongoose.connect("mongodb://localhost:27017/mydb", {
    useNewUrlParser: true,
    useUnifiedTopology: true,
  });

  const db = mongoose.connection;
  db.on("error", console.error.bind(console, "connection error:"));
  db.once("open", () => {
    console.log("Connected to MongoDB");
  });
  ```
- **Defining a Model**:
  ```javascript
  const User = mongoose.model("User", {
    name: String,
    age: Number,
  });

  const newUser = new User({ name: "John", age: 30 });
  newUser.save().then(() => console.log("User saved!"));
  ```

---

## 6. **Environment Variables**
- **Using dotenv**:
  ```javascript
  require("dotenv").config();

  const PORT = process.env.PORT || 3000;
  console.log(`Server running on port ${PORT}`);
  ```

---

## 7. **JWT Authentication**
- **Generating Tokens**:
  ```javascript
  const jwt = require("jsonwebtoken");

  const token = jwt.sign({ id: 123 }, "secretkey", { expiresIn: "1h" });
  console.log(token);
  ```
- **Verifying Tokens**:
  ```javascript
  const decoded = jwt.verify(token, "secretkey");
  console.log(decoded);
  ```

---

## 8. **API Testing**
- **Using Postman or Curl**:
  ```bash
  curl -X GET http://localhost:3000/
  curl -X POST http://localhost:3000/data -H "Content-Type: application/json" -d '{"key":"value"}'
  ```

---

## 9. **Debugging**
- **Using Debugger**:
  ```javascript
  debugger;
  ```
  Run the script with `node inspect app.js`.

- **Using Console Logs**:
  ```javascript
  console.log("Debugging information");
  ```

---

## 10. **Deploying**
- **PM2 for Process Management**:
  ```bash
  npm install -g pm2
  pm2 start app.js
  ```
- **Hosting**:
  - Use platforms like Heroku, AWS, or Vercel.
  - Ensure environment variables are set on the platform.

---

This cheatsheet covers essential backend concepts for Node.js and Express.js development. Practice implementing these examples to strengthen your skills!

