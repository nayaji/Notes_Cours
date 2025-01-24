# PHP Cheatsheet: Comprehensive Guide

## 1. **Introduction to PHP**
- **What is PHP?**: PHP (Hypertext Preprocessor) is a server-side scripting language designed for web development.
- **Key Features**:
  - Embeddable in HTML.
  - Supports various databases (e.g., MySQL).
  - Open-source and platform-independent.

---

## 2. **Basic Syntax**
- **PHP Tag**:
  ```php
  <?php
  echo "Hello, World!";
  ?>
  ```
- **Comments**:
  ```php
  // Single-line comment
  # Single-line comment
  /*
     Multi-line comment
  */
  ```
- **Variables**:
  ```php
  $name = "John";
  $age = 25;
  ```

---

## 3. **Data Types**
- **Common Types**:
  - `string`, `integer`, `float`, `boolean`, `array`, `object`, `null`.
- **Example**:
  ```php
  $text = "Hello";  // String
  $num = 42;        // Integer
  $price = 10.5;    // Float
  $isValid = true;  // Boolean
  ```

---

## 4. **Control Structures**
- **Conditionals**:
  ```php
  if ($age > 18) {
      echo "Adult";
  } elseif ($age == 18) {
      echo "Just turned adult";
  } else {
      echo "Minor";
  }
  ```
- **Switch**:
  ```php
  switch ($role) {
      case 'admin':
          echo "Admin Access";
          break;
      case 'editor':
          echo "Editor Access";
          break;
      default:
          echo "Guest Access";
  }
  ```
- **Loops**:
  ```php
  // While Loop
  while ($i < 10) {
      echo $i++;
  }

  // For Loop
  for ($i = 0; $i < 10; $i++) {
      echo $i;
  }

  // Foreach Loop
  $arr = ["Apple", "Banana", "Cherry"];
  foreach ($arr as $fruit) {
      echo $fruit;
  }
  ```

---

## 5. **Functions**
- **Defining and Calling**:
  ```php
  function greet($name) {
      return "Hello, $name!";
  }

  echo greet("Alice");
  ```
- **Default Parameters**:
  ```php
  function greet($name = "Guest") {
      return "Hello, $name!";
  }

  echo greet(); // Outputs: Hello, Guest!
  ```

---

## 6. **Arrays**
- **Indexed Arrays**:
  ```php
  $fruits = ["Apple", "Banana", "Cherry"];
  echo $fruits[0]; // Outputs: Apple
  ```
- **Associative Arrays**:
  ```php
  $person = ["name" => "Alice", "age" => 30];
  echo $person['name']; // Outputs: Alice
  ```
- **Multi-dimensional Arrays**:
  ```php
  $matrix = [
      [1, 2, 3],
      [4, 5, 6],
  ];
  echo $matrix[1][2]; // Outputs: 6
  ```

---

## 7. **Superglobals**
- **Common Superglobals**:
  - `$_GET`: Retrieve data from URL query parameters.
  - `$_POST`: Retrieve data from form submissions.
  - `$_SESSION`: Manage session data.
  - `$_COOKIE`: Access cookies.
- **Example**:
  ```php
  echo $_GET['username'];
  ```

---

## 8. **Forms and Validation**
- **Basic Form Handling**:
  ```php
  <form method="POST" action="">
      <input type="text" name="username">
      <button type="submit">Submit</button>
  </form>

  <?php
  if ($_SERVER['REQUEST_METHOD'] == 'POST') {
      $username = $_POST['username'];
      echo "Hello, $username!";
  }
  ?>
  ```
- **Validation**:
  ```php
  if (empty($username)) {
      echo "Username is required!";
  }
  ```

---

## 9. **File Handling**
- **Read File**:
  ```php
  $content = file_get_contents("file.txt");
  echo $content;
  ```
- **Write File**:
  ```php
  file_put_contents("file.txt", "Hello, World!");
  ```
- **File Upload**:
  ```php
  <form method="POST" enctype="multipart/form-data">
      <input type="file" name="file">
      <button type="submit">Upload</button>
  </form>

  <?php
  if ($_FILES['file']['error'] == 0) {
      move_uploaded_file($_FILES['file']['tmp_name'], "uploads/" . $_FILES['file']['name']);
      echo "File uploaded!";
  }
  ?>
  ```

---

## 10. **Database Interaction (MySQL)**
- **Connect to Database**:
  ```php
  $conn = new mysqli("localhost", "username", "password", "database");
  if ($conn->connect_error) {
      die("Connection failed: " . $conn->connect_error);
  }
  ```
- **Query Database**:
  ```php
  $result = $conn->query("SELECT * FROM users");
  while ($row = $result->fetch_assoc()) {
      echo $row['name'];
  }
  ```
- **Prepared Statements**:
  ```php
  $stmt = $conn->prepare("INSERT INTO users (name, age) VALUES (?, ?)");
  $stmt->bind_param("si", $name, $age);
  $stmt->execute();
  ```

---

## 11. **Sessions and Cookies**
- **Start Session**:
  ```php
  session_start();
  $_SESSION['user'] = "Alice";
  echo $_SESSION['user'];
  ```
- **Set and Get Cookies**:
  ```php
  setcookie("user", "Alice", time() + (86400 * 30));
  echo $_COOKIE['user'];
  ```

---

## 12. **Error Handling**
- **Try/Catch**:
  ```php
  try {
      throw new Exception("Something went wrong");
  } catch (Exception $e) {
      echo $e->getMessage();
  }
  ```
- **Custom Error Handler**:
  ```php
  function customError($errno, $errstr) {
      echo "Error: [$errno] $errstr";
  }
  set_error_handler("customError");
  ```

---

## 13. **Best Practices**
- Always sanitize user inputs using `htmlspecialchars()` or `filter_input()`.
- Use prepared statements to prevent SQL injection.
- Separate business logic from presentation.
- Keep sensitive data (e.g., database credentials) outside the webroot.

---

This cheatsheet provides a comprehensive overview of PHP for developing dynamic and secure web applications. Experiment with the examples and apply them to real-world projects!

