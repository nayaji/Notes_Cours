# JavaScript Cheatsheet: Frontend Guide

## 1. **Basics**
- **Variables**:
  ```javascript
  let x = 10; // Block-scoped
  const y = 20; // Immutable
  var z = 30; // Function-scoped
  ```
- **Data Types**: `string`, `number`, `boolean`, `undefined`, `null`, `object`, `symbol`.
- **Template Literals**:
  ```javascript
  const greeting = `Hello, ${name}!`;
  ```
- **Type Conversion**:
  ```javascript
  Number("42"); // Converts to number
  String(42);    // Converts to string
  Boolean(0);    // Converts to boolean
  ```

---

## 2. **DOM Manipulation**
- **Selecting Elements**:
  ```javascript
  document.getElementById("id");
  document.querySelector(".class");
  document.querySelectorAll("div");
  ```
- **Modifying Content**:
  ```javascript
  element.textContent = "New Text";
  element.innerHTML = "<b>Bold Text</b>";
  ```
- **Attributes**:
  ```javascript
  element.setAttribute("name", "value");
  element.getAttribute("name");
  ```
- **Classes**:
  ```javascript
  element.classList.add("new-class");
  element.classList.remove("old-class");
  element.classList.toggle("active");
  ```

---

## 3. **Events**
- **Adding Event Listeners**:
  ```javascript
  element.addEventListener("click", () => {
    console.log("Clicked!");
  });
  ```
- **Common Events**: `click`, `mouseover`, `keydown`, `keyup`, `submit`, `load`, `resize`.
- **Event Delegation**:
  ```javascript
  document.querySelector(".parent").addEventListener("click", (event) => {
    if (event.target.matches(".child")) {
      console.log("Child clicked!");
    }
  });
  ```

---

## 4. **Fetch API (AJAX)**
- **Basic Usage**:
  ```javascript
  fetch("https://api.example.com/data")
    .then((response) => response.json())
    .then((data) => console.log(data))
    .catch((error) => console.error(error));
  ```
- **Async/Await**:
  ```javascript
  async function fetchData() {
    try {
      const response = await fetch("https://api.example.com/data");
      const data = await response.json();
      console.log(data);
    } catch (error) {
      console.error(error);
    }
  }
  fetchData();
  ```

---

## 5. **Forms and Validation**
- **Accessing Inputs**:
  ```javascript
  const input = document.querySelector("#myInput").value;
  ```
- **Validation**:
  ```javascript
  if (!input) {
    console.error("Input is required!");
  }
  ```
- **Preventing Default Behavior**:
  ```javascript
  form.addEventListener("submit", (event) => {
    event.preventDefault();
  });
  ```

---

## 6. **Timers**
- **Set Timeout**:
  ```javascript
  setTimeout(() => {
    console.log("Delayed message");
  }, 1000); // 1 second
  ```
- **Set Interval**:
  ```javascript
  const interval = setInterval(() => {
    console.log("Repeating message");
  }, 1000);

  clearInterval(interval); // Stops the interval
  ```

---

## 7. **LocalStorage and SessionStorage**
- **Set and Get Items**:
  ```javascript
  localStorage.setItem("key", "value");
  const value = localStorage.getItem("key");

  sessionStorage.setItem("key", "value");
  ```
- **Remove Items**:
  ```javascript
  localStorage.removeItem("key");
  ```

---

## 8. **ES6+ Features**
- **Arrow Functions**:
  ```javascript
  const add = (a, b) => a + b;
  ```
- **Destructuring**:
  ```javascript
  const { name, age } = person;
  ```
- **Spread and Rest Operators**:
  ```javascript
  const newArr = [...oldArr, 4, 5];
  function sum(...numbers) {
    return numbers.reduce((a, b) => a + b);
  }
  ```

---

## 9. **Modules**
- **Export/Import**:
  ```javascript
  // module.js
  export const greet = () => console.log("Hello!");

  // main.js
  import { greet } from "./module.js";
  greet();
  ```

---

## 10. **Common Utilities**
- **Console Methods**:
  ```javascript
  console.log("Info");
  console.warn("Warning");
  console.error("Error");
  ```
- **Math**:
  ```javascript
  Math.random();
  Math.floor(Math.random() * 10);
  ```
- **Date**:
  ```javascript
  const now = new Date();
  now.toLocaleDateString();
  ```

---

## 11. **Debugging Tips**
- Use `console.log()` to trace variables.
- Add `debugger` to pause script execution.
- Utilize browser developer tools for breakpoints.

---

This cheatsheet serves as a handy guide to essential JavaScript concepts and features for frontend development. Experiment with code examples and build projects to reinforce your understanding!

