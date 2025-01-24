# Express.js Cheatsheet: Comprehensive Guide

## 1. **Setting Up Express.js**
- **Install Express**:
  ```bash
  npm install express
  ```
- **Basic Server Setup**:
  ```javascript
  const express = require("express");
  const app = express();

  app.listen(3000, () => {
    console.log("Server running on port 3000");
  });
  ```

---

## 2. **Middleware**
- **Using Middleware**:
  ```javascript
  app.use((req, res, next) => {
    console.log(`${req.method} ${req.url}`);
    next();
  });
  ```
- **Built-in Middleware**:
  ```javascript
  app.use(express.json());       // Parses JSON bodies
  app.use(express.urlencoded({ extended: true })); // Parses URL-encoded bodies
  app.use(express.static("public")); // Serves static files from "public" folder
  ```
- **Third-Party Middleware**:
  ```bash
  npm install morgan cors
  ```
  ```javascript
  const morgan = require("morgan");
  const cors = require("cors");

  app.use(morgan("dev"));
  app.use(cors());
  ```

---

## 3. **Routing**
- **Basic Routes**:
  ```javascript
  app.get("/", (req, res) => {
    res.send("Welcome to Express!");
  });

  app.post("/submit", (req, res) => {
    res.json({ message: "Data received", data: req.body });
  });
  ```
- **Route Parameters**:
  ```javascript
  app.get("/user/:id", (req, res) => {
    res.send(`User ID: ${req.params.id}`);
  });
  ```
- **Query Parameters**:
  ```javascript
  app.get("/search", (req, res) => {
    res.send(`Search query: ${req.query.q}`);
  });
  ```
- **Grouping Routes with Router**:
  ```javascript
  const router = express.Router();

  router.get("/", (req, res) => res.send("Home Page"));
  router.get("/about", (req, res) => res.send("About Page"));

  app.use("/pages", router);
  ```

---

## 4. **Error Handling**
- **Default Error Handler**:
  ```javascript
  app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send("Something went wrong!");
  });
  ```
- **Custom 404 Handler**:
  ```javascript
  app.use((req, res) => {
    res.status(404).send("Page not found");
  });
  ```

---

## 5. **Request and Response**
- **Access Request Data**:
  ```javascript
  app.post("/login", (req, res) => {
    const username = req.body.username;
    res.send(`Welcome, ${username}`);
  });
  ```
- **Set Response Headers**:
  ```javascript
  res.set("Content-Type", "application/json");
  ```
- **Response Methods**:
  ```javascript
  res.send("Hello");          // Sends plain text
  res.json({ key: "value" }); // Sends JSON
  res.status(404).send("Not found");
  ```

---

## 6. **Static Files**
- **Serve Static Files**:
  ```javascript
  app.use(express.static("public"));
  ```
  - Files in the `public` directory (e.g., `public/index.html`) are accessible via `/index.html`.

---

## 7. **Template Engines**
- **Setting Up EJS**:
  ```bash
  npm install ejs
  ```
  ```javascript
  app.set("view engine", "ejs");

  app.get("/template", (req, res) => {
    res.render("template", { title: "Express Template", message: "Hello, EJS!" });
  });
  ```

---

## 8. **Working with Databases**
- **MongoDB Example**:
  ```bash
  npm install mongoose
  ```
  ```javascript
  const mongoose = require("mongoose");

  mongoose.connect("mongodb://localhost:27017/mydb", {
    useNewUrlParser: true,
    useUnifiedTopology: true,
  });

  const User = mongoose.model("User", { name: String, age: Number });

  app.post("/users", async (req, res) => {
    const user = new User(req.body);
    await user.save();
    res.send(user);
  });
  ```

---

## 9. **Security Best Practices**
- **Helmet for Security Headers**:
  ```bash
  npm install helmet
  ```
  ```javascript
  const helmet = require("helmet");
  app.use(helmet());
  ```
- **Sanitize Input**:
  ```bash
  npm install express-mongo-sanitize
  ```
  ```javascript
  const mongoSanitize = require("express-mongo-sanitize");
  app.use(mongoSanitize());
  ```
- **Rate Limiting**:
  ```bash
  npm install express-rate-limit
  ```
  ```javascript
  const rateLimit = require("express-rate-limit");

  const limiter = rateLimit({
    windowMs: 15 * 60 * 1000, // 15 minutes
    max: 100, // Limit each IP to 100 requests per windowMs
  });
  app.use(limiter);
  ```

---

## 10. **Testing APIs**
- **Using Postman or Curl**:
  ```bash
  curl -X GET http://localhost:3000/
  curl -X POST http://localhost:3000/login -H "Content-Type: application/json" -d '{"username":"admin"}'
  ```

- **Automated Testing with Jest**:
  ```bash
  npm install jest supertest
  ```
  ```javascript
  const request = require("supertest");
  const app = require("../app");

  test("GET /", async () => {
    const res = await request(app).get("/");
    expect(res.statusCode).toBe(200);
    expect(res.text).toBe("Welcome to Express!");
  });
  ```

---

## 11. **Deploying Express Apps**
- **Using PM2**:
  ```bash
  npm install -g pm2
  pm2 start app.js
  ```
- **Hosting Platforms**:
  - Deploy on platforms like Heroku, AWS, or Vercel.
  - Ensure environment variables are set on the platform.

---

This cheatsheet is a comprehensive guide to mastering Express.js. Practice these concepts in real-world projects to solidify your understanding!

