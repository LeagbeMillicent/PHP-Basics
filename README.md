# PHP-Basics

# Introduction
PHP is an acronym for "PHP: Hypertext Preprocessor". 
PHP is a widely-used, open source scripting language. 
PHP scripts are executed on the server. 
PHP is free to download and use. 
PHP is a powerful tool for making dynamic and interactive Web pages.

# Setting Up 
To start using PHP, you can:
Install a web server on your own PC, and then install PHP and MySQL "apachefriends.org".
Note: Installation should be done on the C:Disk

# IDE : VS Code

# PHP Basics

## Variable, Data Type, Array Type, Object Type

A PHP script starts with `<?php` and ends with `?>`.

### Example 1:
```php
<?php
   // PHP codes go here
?>
```

### Example 2:
```html
<!DOCTYPE html>
<html>
<body>

<h1>My first PHP page</h1>

<?php
echo "Hello World!";
?>

</body>
</html>
```

---
## Comments in PHP
A comment in PHP code is a line that is not executed as part of the program. It helps in understanding the code and can also be used to temporarily disable code execution.

### Example:
```php
// This is a single-line comment

# This is also a single-line comment

/* This is a
   multi-line comment */
```

---
## Declaring PHP Variables
In PHP, a variable starts with the `$` sign, followed by the variable name.

### Example:
```php
$x = 5;
$y = "John";
```

### Rules for PHP Variables:
- A variable starts with `$`, followed by its name.
- A variable name must start with a letter or an underscore (`_`).
- A variable name cannot start with a number.
- A variable name can contain alphanumeric characters and underscores (A-z, 0-9, and `_`).
- Variable names are case-sensitive (`$age` and `$AGE` are different variables).

**Note:** PHP variable names are case-sensitive!

### Outputting Variables
```php
$txt = "Programming in PHP!";
echo "I love $txt!";
```

---
## PHP Data Types
PHP supports the following data types:
- **String**
- **Integer**
- **Float** (floating point numbers, also called double)
- **Boolean**
- **Array**
- **Object**
- **NULL**
- **Resource**

To check the data type of a variable, use the `var_dump()` function.

### Example:
```php
$x = 5;
var_dump($x);
```

---
## Variable Scope in PHP
PHP has three types of variable scopes:
- **Local**
- **Global**
- **Static**

### Global and Local Scope Example:
```php
$x = 5; // global scope

function myTest() {
  // using x inside this function will generate an error
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

echo "<p>Variable x outside function is: $x</p>";
```

### Using `global` Keyword:
```php
$x = 5;
$y = 10;

function myTest() {
  global $x, $y;
  $y = $x + $y;
}

myTest();
echo $y; // outputs 15
```

### Using `$GLOBALS` Array:
```php
$x = 5;
$y = 10;

function myTest() {
  $GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];
}

myTest();
echo $y; // outputs 15
```

### Static Variables:
```php
function myTest() {
  static $x = 0;
  echo $x;
  $x++;
}

myTest();
myTest();
myTest();
```

---
## PHP `echo` / `print`
Both `echo` and `print` are used to output data to the screen.

### Example:
```php
echo "Hello";
// Same as:
echo("Hello");
```

### Display Text with `echo`:
```php
echo "<h2>PHP is Fun!</h2>";
echo "Hello world!<br>";
echo "I'm about to learn PHP!<br>";
```

### Display Variables with `echo`:
```php
$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";

echo "<h2>$txt1</h2>";
echo "<p>Study PHP at $txt2</p>";
```

### Display Text with `print`:
```php
print "<h2>PHP is Fun!</h2>";
print "Hello world!<br>";
print "I'm about to learn PHP!";
```

---
## PHP Strings
A string is a sequence of characters.

### Example:
```php
$x = "Hello world!";
$y = 'Hello world!';

var_dump($x);
echo "<br>";
var_dump($y);
```

### String Functions:
#### Get String Length:
```php
echo strlen("Hello world!");
```

#### Convert to Uppercase:
```php
$x = "Hello World!";
echo strtoupper($x);
```

#### Convert to Lowercase:
```php
$x = "Hello World!";
echo strtolower($x);
```

#### Replace String:
```php
$x = "Hello World!";
echo str_replace("World", "Dolly", $x);
```

#### Remove Whitespace:
```php
$x = " Hello World! ";
echo trim($x);
```

#### String Concatenation:
```php
$x = "Hello";
$y = "World";
$z = $x . " " . $y;
echo $z;
```

---
## PHP Numbers
### PHP Integer
```php
$x = 5985;
var_dump($x);
```

### PHP Float
```php
$x = 10.365;
var_dump($x);
```

### PHP Boolean
```php
$x = true;
var_dump($x);
```

### PHP Array
```php
$cars = array("Volvo", "BMW", "Toyota");
var_dump($cars);
```

---
## PHP Object
### Example:
```php
class Car {
  public $color;
  public $model;
  public function __construct($color, $model) {
    $this->color = $color;
    $this->model = $model;
  }
  public function message() {
    return "My car is a " . $this->color . " " . $this->model . "!";
  }
}

$myCar = new Car("red", "Volvo");
var_dump($myCar);
```

---
## PHP Casting
### Cast Float and String to Integer:
```php
// Cast float to int
$x = 23465.768;
$int_cast = (int)$x;
echo $int_cast;

echo "<br>";

// Cast string to int
$x = "23465.768";
$int_cast = (int)$x;
echo $int_cast;
```

---


# 🚀 PHP Type Casting Guide

Type casting in PHP allows you to **convert variables** from one data type to another using **explicit casting**.

---

## 📌 Cast to String
To cast a value to a **string**, use the `(string)` statement:

```php
$a = 5;       // Integer
$b = 5.34;    // Float
$c = "hello"; // String
$d = true;    // Boolean
$e = NULL;    // NULL

$a = (string) $a;
$b = (string) $b;
$c = (string) $c;
$d = (string) $d;
$e = (string) $e;

// Verify data type
var_dump($a, $b, $c, $d, $e);



# 🌍 PHP Superglobals

Superglobals are **built-in variables** in PHP that are accessible **anywhere** in a script, regardless of scope (global or local). They provide an easy way to handle requests, sessions, cookies, and server-related information.

## 🔹 List of PHP Superglobals  

| Super Global  | Description |
|--------------|------------|
| `$_GET`      | Retrieves data sent via URL parameters (query string) |
| `$_POST`     | Retrieves data from form submissions using the `POST` method |
| `$_REQUEST`  | Collects data from `GET`, `POST`, and `COOKIE` methods |
| `$_SERVER`   | Provides server and execution environment information |
| `$_FILES`    | Handles file uploads |
| `$_ENV`      | Contains environment variables |
| `$_COOKIE`   | Stores cookies sent by the client |
| `$_SESSION`  | Stores session variables for users |

---

## 📌 `$_GET` - Access URL Parameters  
Used to collect data sent via the **query string** in the URL.

🔹 **Example:**  
URL: `http://example.com/index.php?name=John&age=30`
```php
echo "Name: " . $_GET['name'] . "<br>";
echo "Age: " . $_GET['age'];

### PHP Constants

A constant is an identifier (name) for a simple value. The value cannot be changed during the script.

A valid constant name starts with a letter or underscore (no $ sign before the constant name).

**Note:** Unlike variables, constants are automatically global across the entire script.

### Create a PHP Constant
To create a constant, use the `define()` function.

#### Syntax:
```php
define(name, value);
```

**Parameters:**
- `name`: Specifies the name of the constant
- `value`: Specifies the value of the constant

#### Example:
```php
define("GREETING", "Welcome to W3Schools.com!");
echo GREETING;
```

## PHP Constant Arrays
From PHP 7, you can create an Array constant using the `define()` function.

#### Example:
Create an Array constant:
```php
define("cars", [
  "Alfa Romeo",
  "BMW",
  "Toyota"
]);
echo cars[0];
```

# PHP Operators
Operators are used to perform operations on variables and values.

PHP divides the operators into the following groups:
- Arithmetic operators
- Assignment operators
- Comparison operators
- Increment/Decrement operators
- Logical operators
- String operators
- Array operators
- Conditional assignment operators

## PHP Arithmetic Operators
The PHP arithmetic operators are used with numeric values to perform common arithmetical operations, such as addition, subtraction, multiplication, etc.

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `+` | Addition | `$x + $y` | Sum of `$x` and `$y` |
| `-` | Subtraction | `$x - $y` | Difference of `$x` and `$y` |
| `*` | Multiplication | `$x * $y` | Product of `$x` and `$y` |
| `/` | Division | `$x / $y` | Quotient of `$x` and `$y` |
| `%` | Modulus | `$x % $y` | Remainder of `$x` divided by `$y` |
| `**` | Exponentiation | `$x ** $y` | `$x` raised to the power of `$y` |

## PHP Assignment Operators
The PHP assignment operators are used with numeric values to assign values to variables.

| Assignment | Same as... | Description |
|------------|-----------|-------------|
| `x = y` | `x = y` | Assigns value of `y` to `x` |
| `x += y` | `x = x + y` | Addition assignment |
| `x -= y` | `x = x - y` | Subtraction assignment |
| `x *= y` | `x = x * y` | Multiplication assignment |
| `x /= y` | `x = x / y` | Division assignment |
| `x %= y` | `x = x % y` | Modulus assignment |

## PHP Comparison Operators
The PHP comparison operators are used to compare two values (number or string):

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `==` | Equal | `$x == $y` | True if `$x` is equal to `$y` |
| `===` | Identical | `$x === $y` | True if `$x` is equal to `$y`, and they are of the same type |
| `!=` | Not equal | `$x != $y` | True if `$x` is not equal to `$y` |
| `<>` | Not equal | `$x <> $y` | True if `$x` is not equal to `$y` |
| `!==` | Not identical | `$x !== $y` | True if `$x` is not equal to `$y`, or they are not of the same type |
| `>` | Greater than | `$x > $y` | True if `$x` is greater than `$y` |
| `<` | Less than | `$x < $y` | True if `$x` is less than `$y` |
| `>=` | Greater than or equal to | `$x >= $y` | True if `$x` is greater than or equal to `$y` |
| `<=` | Less than or equal to | `$x <= $y` | True if `$x` is less than or equal to `$y` |

## PHP Logical Operators
The PHP logical operators are used to combine conditional statements.

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `and` | And | `$x and $y` | True if both `$x` and `$y` are true |
| `or` | Or | `$x or $y` | True if either `$x` or `$y` is true |
| `xor` | Xor | `$x xor $y` | True if either `$x` or `$y` is true, but not both |
| `&&` | And | `$x && $y` | True if both `$x` and `$y` are true |
| `||` | Or | `$x || $y` | True if either `$x` or `$y` is true |
| `!` | Not | `!$x` | True if `$x` is not true |

## PHP Conditional Statements
Conditional statements allow different actions for different conditions.

- `if` statement - executes some code if one condition is true
- `if...else` statement - executes one block if condition is true, another if false
- `if...elseif...else` statement - multiple conditions
- `switch` statement - selects one of many blocks of code

### Example:
```php
$t = date("H");

if ($t < "10") {
  echo "Good morning!";
} elseif ($t < "20") {
  echo "Good day!";
} else {
  echo "Good night!";
}
```

## PHP Loops
Loops execute a block of code multiple times.

- `while` - loops while a condition is true
- `do...while` - executes at least once, then repeats if condition is true
- `for` - loops a set number of times
- `foreach` - loops through an array

### Example (for loop):
```php
for ($x = 0; $x <= 10; $x++) {
  echo "The number is: $x <br>";
}
```

### Example (foreach loop):
```php
$colors = array("red", "green", "blue");
foreach ($colors as $color) {
  echo "$color <br>";
}
```

### HTML FORMS
Reference to W3Schools : https://www.w3schools.com/html/html_forms.asp



### Handling Form Submission
```php
<?php
// define variables and set to empty values
$name = $email = $gender = $comment = $website = "";
$name, $email, $gender, $comment, $website
```
These are initialized as empty strings.
This prevents errors if no data is submitted.

3. Handling the Form Submission ($_SERVER["REQUEST_METHOD"])
```php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}
$_SERVER["REQUEST_METHOD"] → Checks how the form is submitted.
"POST" means the form was submitted using the POST method.
$_POST["name"] → Retrieves the value of the name field from the form.
test_input() → This function cleans the input before storing it.

```
4. Input Sanitization with test_input()
``` php
function test_input($data) {
  $data = trim($data);            // Removes unnecessary spaces
  $data = stripslashes($data);    // Removes backslashes (\)
  $data = htmlspecialchars($data);// Converts special characters to HTML entities
  return $data;
}

```
Purpose: Prevents security issues like Cross-Site Scripting (XSS) and improper input formatting.
trim() → Removes whitespace from the beginning and end.
stripslashes() → Removes backslashes (\) to prevent escaping attacks.
htmlspecialchars() → Converts <, >, ", ', & into HTML entities to prevent malicious code injection.
5. HTML Form
```html
<h2>PHP Form Validation Example</h2>
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">  
<form> → Creates an HTML form.
method="post" → Submits form data using the POST method.
action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>"
$_SERVER["PHP_SELF"] → Submits the form to the same page.
htmlspecialchars() → Prevents security vulnerabilities like XSS attacks.
```
6. Form Fields
```html

  Name: <input type="text" name="name">
  <br><br>
  E-mail: <input type="text" name="email">
  <br><br>
  Website: <input type="text" name="website">
  <br><br>
  Comment: <textarea name="comment" rows="5" cols="40"></textarea>
  <br><br>
<input type="text" name="name"> → A text input field for the name.
<textarea> → A multi-line input field for the comment.
```
7. Radio Buttons for Gender Selection
```html
  Gender:
  <input type="radio" name="gender" value="female">Female
  <input type="radio" name="gender" value="male">Male
  <input type="radio" name="gender" value="other">Other
  <br><br>
```
Radio buttons let users select one option from three choices (Female, Male, Other).
name="gender" → Ensures only one option can be selected.
8. Submit Button
```html
  <input type="submit" name="submit" value="Submit">  
</form>
<input type="submit"> → Submits the form.
name="submit" →
```
Helps identify when the form is submitted.
9. Displaying Submitted Data
```php
<?php
echo "<h2>Your Input:</h2>";
echo $name;
echo "<br>";
echo $email;
echo "<br>";
echo $website;
echo "<br>";
echo $comment;
echo "<br>";
echo $gender;
?>
```
Displays user input after submission.
Each variable ($name, $email, etc.) is echoed inside <br> tags for better readability.
How This Works in Action
User fills out the form and clicks Submit.
The data is sent via POST to the same page (action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>").
PHP sanitizes the input (test_input()).
The values are stored in variables ($name, $email, etc.).
The submitted data is displayed below the form

## Warning!
The $_SERVER["PHP_SELF"] variable can be used by hackers!

If PHP_SELF is used in your page then a user can enter a slash / and then some Cross Site Scripting (XSS) commands to execute.

Cross-site scripting (XSS) is a type of computer security vulnerability typically found in Web applications. XSS enables attackers to inject client-side script into Web pages viewed by other users.

Assume we have the following form in a page named "test_form.php":

<form method="post" action="<?php echo $_SERVER["PHP_SELF"];?>">
Now, if a user enters the normal URL in the address bar like "http://www.example.com/test_form.php", the above code will be translated to:

<form method="post" action="test_form.php">
So far, so good.

However, consider that a user enters the following URL in the address bar:

http://www.example.com/test_form.php/%22%3E%3Cscript%3Ealert('hacked')%3C/script%3E
In this case, the above code will be translated to:

<form method="post" action="test_form.php/"><script>alert('hacked')</script>
This code adds a script tag and an alert command. And when the page loads, the JavaScript code will be executed (the user will see an alert box). This is just a simple and harmless example how the PHP_SELF variable can be exploited.

Be aware of that any JavaScript code can be added inside the <script> tag! A hacker can redirect the user to a file on another server, and that file can hold malicious code that can alter the global variables or submit the form to another address to save the user data, for example.

How To Avoid $_SERVER["PHP_SELF"] Exploits?
$_SERVER["PHP_SELF"] exploits can be avoided by using the htmlspecialchars() function.

The form code should look like this:

<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
The htmlspecialchars() function converts special characters to HTML entities. Now if the user tries to exploit the PHP_SELF variable, it will result in the following output:

<form method="post" action="test_form.php/&quot;&gt;&lt;script&gt;alert('hacked')&lt;/script&gt;">
The exploit attempt fails, and no harm is done!

## Validate Form Data With PHP
The first thing we will do is to pass all variables through PHP's htmlspecialchars() function.

When we use the htmlspecialchars() function; then if a user tries to submit the following in a text field:

<script>location.href('http://www.hacked.com')</script>
- this would not be executed, because it would be saved as HTML escaped code, like this:

&lt;script&gt;location.href('http://www.hacked.com')&lt;/script&gt;
The code is now safe to be displayed on a page or inside an e-mail.

We will also do two more things when the user submits the form:

Strip unnecessary characters (extra space, tab, newline) from the user input data (with the PHP trim() function)
Remove backslashes \ from the user input data (with the PHP stripslashes() function)
The next step is to create a function that will do all the checking for us (which is much more convenient than writing the same code over and over again).

We will name the function test_input().

Now, we can check each $_POST variable with the test_input() function, and the script looks like this:

Example:
```php
// define variables and set to empty values
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}

```
Notice that at the start of the script, we check whether the form has been submitted using $_SERVER["REQUEST_METHOD"]. If the REQUEST_METHOD is POST, then the form has been submitted - and it should be validated. If it has not been submitted, skip the validation and display a blank form.


