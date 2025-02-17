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



## Handling Form Submission
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


## PHP Functions

The real power of PHP comes from its functions.

PHP has more than **1000 built-in functions**, and in addition, you can create your own custom functions.

---

### PHP Built-in Functions
PHP has over **1000 built-in functions** that can be called directly from within a script to perform a specific task.

> Please check out our **PHP reference** for a complete overview of the PHP built-in functions.

---

### PHP User Defined Functions
Besides the built-in PHP functions, it is possible to create your own functions.

- A function is a **block of statements** that can be used repeatedly in a program.
- A function **will not execute automatically** when a page loads.
- A function will be executed by a **call to the function**.

#### Create a Function
A user-defined function declaration starts with the keyword `function`, followed by the **name of the function**:

```php
function myMessage() {
  echo "Hello world!";
}
```

> **Note:** A function name must start with a **letter or an underscore**. Function names are **NOT case-sensitive**.

**Tip:** Give the function a name that reflects what the function does!

#### Call a Function
To call the function, just write its name followed by parentheses `()`:

```php
function myMessage() {
  echo "Hello world!";
}

myMessage();
```

The function **outputs "Hello world!"**.

---

### PHP Function Arguments
Information can be passed to functions through **arguments**.

#### Example: Function with One Argument
```php
function familyName($fname) {
  echo "$fname Refsnes.<br>";
}

familyName("Jani");
familyName("Hege");
familyName("Stale");
familyName("Kai Jim");
familyName("Borge");
```

#### Example: Function with Two Arguments
```php
function familyName($fname, $year) {
  echo "$fname Refsnes. Born in $year <br>";
}

familyName("Hege", "1975");
familyName("Stale", "1978");
familyName("Kai Jim", "1983");
```

---

### PHP Default Argument Value
A function can have a **default parameter**:

```php
function setHeight($minheight = 50) {
  echo "The height is : $minheight <br>";
}

setHeight(350);
setHeight(); // will use the default value of 50
setHeight(135);
setHeight(80);
```

---

### PHP Functions - Returning Values
To **return a value**, use the `return` statement:

```php
function sum($x, $y) {
  $z = $x + $y;
  return $z;
}

echo "5 + 10 = " . sum(5, 10) . "<br>";
echo "7 + 13 = " . sum(7, 13) . "<br>";
echo "2 + 4 = " . sum(2, 4);
```

---

### Passing Arguments by Reference
By default, function arguments are passed **by value**.
To pass **by reference**, use the `&` operator:

```php
function add_five(&$value) {
  $value += 5;
}

$num = 2;
add_five($num);
echo $num;
```

---

### Variable Number of Arguments
Use `...` to accept an unknown number of arguments (**variadic function**):

```php
function sumMyNumbers(...$x) {
  $n = 0;
  foreach($x as $num) {
    $n += $num;
  }
  return $n;
}

echo sumMyNumbers(5, 2, 6, 2, 7, 7);
```

> **Note:** You can only have **one** variadic argument, and it must be **the last argument**.

#### Correct Example:
```php
function myFamily($lastname, ...$firstname) {
  $txt = "";
  foreach($firstname as $name) {
    $txt .= "Hi, $name $lastname.<br>";
  }
  return $txt;
}

echo myFamily("Doe", "Jane", "John", "Joey");
```

#### Incorrect Example (will raise an error):
```php
function myFamily(...$firstname, $lastname) { // ERROR
  // Function code
}
```

---

### PHP is a Loosely Typed Language
PHP automatically assigns a **data type** to variables based on their values.

#### Example: Without `strict`
```php
function addNumbers(int $a, int $b) {
  return $a + $b;
}

echo addNumbers(5, "5 days");
// Output: 10 (PHP converts "5 days" to int(5))
```

#### Example: With `strict`
```php
<?php declare(strict_types=1);
function addNumbers(int $a, int $b) {
  return $a + $b;
}

echo addNumbers(5, "5 days"); // Error: Type mismatch
?>
```

---

### PHP Return Type Declarations
In PHP 7+, you can **declare return types**:

```php
<?php declare(strict_types=1);
function addNumbers(float $a, float $b) : float {
  return $a + $b;
}

echo addNumbers(1.2, 5.2);
?>
```

You can specify a different return type than the argument types:

```php
<?php declare(strict_types=1);
function addNumbers(float $a, float $b) : int {
  return (int)($a + $b);
}

echo addNumbers(1.2, 5.2); // Output: 6
?>
```

---


## PHP Functions

The real power of PHP comes from its functions.

PHP has more than **1000 built-in functions**, and in addition, you can create your own custom functions.

---

### PHP Built-in Functions
PHP has over **1000 built-in functions** that can be called directly from within a script to perform a specific task.

> Please check out our **PHP reference** for a complete overview of the PHP built-in functions.

---

### PHP User Defined Functions
Besides the built-in PHP functions, it is possible to create your own functions.

- A function is a **block of statements** that can be used repeatedly in a program.
- A function **will not execute automatically** when a page loads.
- A function will be executed by a **call to the function**.

#### Create a Function
A user-defined function declaration starts with the keyword `function`, followed by the **name of the function**:

```php
function myMessage() {
  echo "Hello world!";
}
```

> **Note:** A function name must start with a **letter or an underscore**. Function names are **NOT case-sensitive**.

**Tip:** Give the function a name that reflects what the function does!

#### Call a Function
To call the function, just write its name followed by parentheses `()`:

```php
function myMessage() {
  echo "Hello world!";
}

myMessage();
```

The function **outputs "Hello world!"**.

---

### PHP Function Arguments
Information can be passed to functions through **arguments**.

#### Example: Function with One Argument
```php
function familyName($fname) {
  echo "$fname Refsnes.<br>";
}

familyName("Jani");
familyName("Hege");
familyName("Stale");
familyName("Kai Jim");
familyName("Borge");
```

#### Example: Function with Two Arguments
```php
function familyName($fname, $year) {
  echo "$fname Refsnes. Born in $year <br>";
}

familyName("Hege", "1975");
familyName("Stale", "1978");
familyName("Kai Jim", "1983");
```

---

### PHP Default Argument Value
A function can have a **default parameter**:

```php
function setHeight($minheight = 50) {
  echo "The height is : $minheight <br>";
}

setHeight(350);
setHeight(); // will use the default value of 50
setHeight(135);
setHeight(80);
```

---

### PHP Functions - Returning Values
To **return a value**, use the `return` statement:

```php
function sum($x, $y) {
  $z = $x + $y;
  return $z;
}

echo "5 + 10 = " . sum(5, 10) . "<br>";
echo "7 + 13 = " . sum(7, 13) . "<br>";
echo "2 + 4 = " . sum(2, 4);
```

---

### PHP Arrays

An array stores multiple values in one single variable:

#### Example
```php
$cars = array("Volvo", "BMW", "Toyota");
```

### What is an Array?
An array is a special variable that can hold many values under a single name, and you can access the values by referring to an index number or name.

### PHP Array Types
In PHP, there are three types of arrays:

- **Indexed arrays** - Arrays with a numeric index
- **Associative arrays** - Arrays with named keys
- **Multidimensional arrays** - Arrays containing one or more arrays

### Working With Arrays
In this tutorial, you will learn how to work with arrays, including:

- Create Arrays
- Access Arrays
- Update Arrays
- Add Array Items
- Remove Array Items
- Sort Arrays

### Array Items
Array items can be of any data type.

The most common are **strings and numbers** (int, float), but array items can also be **objects, functions, or even arrays**.

You can have different data types in the same array.

#### Example
Array items of four different data types:

```php
$myArr = array("Volvo", 15, ["apples", "bananas"], "myFunction");
```

### Array Functions
The real strength of PHP arrays is the built-in array functions, like the `count()` function for counting array items:

#### Example
How many items are in the `$cars` array:

```php
$cars = array("Volvo", "BMW", "Toyota");
echo count($cars);
```

> For a complete reference of all array functions, go to "https://www.w3schools.com/php/php_ref_array.asp".

---



# PHP Global Variables - Superglobals

Superglobals were introduced in PHP 4.1.0 and are built-in variables that are always available in all scopes.

## PHP Global Variables - Superglobals

Some predefined variables in PHP are "superglobals," which means that they are always accessible, regardless of scope. You can access them from any function, class, or file without having to do anything special.

The PHP superglobal variables are:

- `$GLOBALS`
- `$_SERVER`
- `$_REQUEST`
- `$_POST`
- `$_GET`
- `$_FILES`
- `$_ENV`
- `$_COOKIE`
- `$_SESSION`

### `$GLOBALS`
`$GLOBALS` is an array that contains all global variables.

#### Global Variables
Global variables can be accessed from any scope. Variables of the outermost scope are automatically global and can be used by any scope, e.g., inside a function.

To use a global variable inside a function, you must either define it as global with the `global` keyword or refer to it using the `$GLOBALS` syntax.

#### Example: Accessing Global Variables
```php
$x = 75;
  
function myfunction() {
  echo $GLOBALS['x'];
}

myfunction();
```
This differs from other programming languages where global variables are available without specifically referring to them as global.

### `$_SERVER`
`$_SERVER` is a PHP super global variable that holds information about headers, paths, and script locations.

#### Example: Using `$_SERVER`
```php
echo $_SERVER['PHP_SELF'];
echo $_SERVER['SERVER_NAME'];
echo $_SERVER['HTTP_HOST'];
echo $_SERVER['HTTP_REFERER'];
echo $_SERVER['HTTP_USER_AGENT'];
echo $_SERVER['SCRIPT_NAME'];
```

### `$_REQUEST`
`$_REQUEST` is a PHP super global variable that contains submitted form data and all cookie data. It combines data from `$_GET`, `$_POST`, and `$_COOKIE`.

#### Example: Using `$_REQUEST`
```php
$name = $_REQUEST['fname'];
echo $name;
```

### `$_POST`
`$_POST` contains an array of variables received via the HTTP POST method.

#### Example: Using `$_POST`
```php
$name = $_POST['fname'];
echo $name;
```

### `$_GET`
`$_GET` contains an array of variables received via the HTTP GET method.

#### Example: Using `$_GET`
```php
<?php
echo "Study " . $_GET["subject"] . " at " . $_GET["web"];
?>
```

---

# PHP Regular Expressions

## What is a Regular Expression?
A regular expression is a sequence of characters that forms a search pattern. It can be a single character or a more complex pattern used for text search and replace operations.

### Syntax
```php
$exp = "/w3schools/i";
```
- `/` is the delimiter
- `w3schools` is the pattern being searched for
- `i` is a modifier making the search case-insensitive

### Regular Expression Functions

| Function | Description |
|----------|-------------|
| `preg_match()` | Returns 1 if the pattern was found in the string, otherwise 0 |
| `preg_match_all()` | Returns the number of times the pattern was found in the string |
| `preg_replace()` | Returns a new string where matched patterns are replaced |

#### Example: Using `preg_match()`
```php
$str = "Visit W3Schools";
$pattern = "/w3schools/i";
echo preg_match($pattern, $str);
```

#### Example: Using `preg_replace()`
```php
$str = "Visit Microsoft!";
$pattern = "/microsoft/i";
echo preg_replace($pattern, "W3Schools", $str);
```

### Regular Expression Modifiers

| Modifier | Description |
|----------|-------------|
| `i` | Case-insensitive search |
| `m` | Multiline search |
| `u` | Enables correct matching of UTF-8 encoded patterns |

### Regular Expression Patterns

| Pattern | Description |
|---------|-------------|
| `[abc]` | Finds one or many of the characters inside the brackets |
| `[^abc]` | Finds any character NOT between the brackets |
| `[a-z]` | Finds any character alphabetically between two letters |
| `[0-9]` | Finds any digit |

### Metacharacters

| Metacharacter | Description |
|--------------|-------------|
| `|` | Finds a match for any one of the patterns separated by `|` |
| `.` | Finds any character |
| `^` | Matches the beginning of a string |
| `$` | Matches the end of a string |

#### Example: Using Metacharacters
```php
$str = "Apples and bananas.";
$pattern = "/ba(na){2}/i";
echo preg_match($pattern, $str);
```

## PHP Date and Time

The PHP `date()` function is used to format a date and/or a time.

### The PHP `date()` Function
The PHP `date()` function formats a timestamp to a more readable date and time.

#### Syntax
```php
date(format, timestamp)
```
- **format** (Required): Specifies the format of the timestamp.
- **timestamp** (Optional): Specifies a timestamp. Default is the current date and time.

A timestamp is a sequence of characters, denoting the date and/or time at which a certain event occurred.

### Get a Date
The required `format` parameter of the `date()` function specifies how to format the date (or time).

Commonly used characters for dates:
- `d` - Day of the month (01 to 31)
- `m` - Month (01 to 12)
- `Y` - Year (in four digits)
- `l` (lowercase 'L') - Day of the week

Other characters like `/`, `.`, or `-` can be inserted for formatting.

#### Example:
```php
<?php
echo "Today is " . date("Y/m/d") . "<br>";
echo "Today is " . date("Y.m.d") . "<br>";
echo "Today is " . date("Y-m-d") . "<br>";
echo "Today is " . date("l");
?>
```

### PHP Tip - Automatic Copyright Year
Use the `date()` function to automatically update the copyright year:
```php
&copy; 2010-<?php echo date("Y");?>
```

### Get a Time
Commonly used characters for times:
- `H` - 24-hour format (00 to 23)
- `h` - 12-hour format (01 to 12)
- `i` - Minutes (00 to 59)
- `s` - Seconds (00 to 59)
- `a` - AM/PM (lowercase)

#### Example:
```php
<?php
echo "The time is " . date("h:i:sa");
?>
```

### Get Your Time Zone
If the time returned is incorrect, set the desired timezone.

#### Example:
```php
<?php
date_default_timezone_set("America/New_York");
echo "The time is " . date("h:i:sa");
?>
```

### Create a Date With `mktime()`
The `mktime()` function returns the Unix timestamp for a given date.

#### Syntax:
```php
mktime(hour, minute, second, month, day, year)
```

#### Example:
```php
<?php
$d = mktime(11, 14, 54, 8, 12, 2014);
echo "Created date is " . date("Y-m-d h:i:sa", $d);
?>
```

### Create a Date From a String With `strtotime()`
The `strtotime()` function converts a human-readable date string into a Unix timestamp.

#### Syntax:
```php
strtotime(time, now)
```

#### Example:
```php
<?php
$d = strtotime("10:30pm April 15 2014");
echo "Created date is " . date("Y-m-d h:i:sa", $d);
?>
```

You can use different values with `strtotime()`:
```php
<?php
echo date("Y-m-d h:i:sa", strtotime("tomorrow")) . "<br>";
echo date("Y-m-d h:i:sa", strtotime("next Saturday")) . "<br>";
echo date("Y-m-d h:i:sa", strtotime("+3 Months")) . "<br>";
?>
```

### More Date Examples
Output dates for the next six Saturdays:
```php
<?php
$startdate = strtotime("Saturday");
$enddate = strtotime("+6 weeks", $startdate);
while ($startdate < $enddate) {
  echo date("M d", $startdate) . "<br>";
  $startdate = strtotime("+1 week", $startdate);
}
?>
```

Calculate the number of days until July 4th:
```php
<?php
$d1 = strtotime("July 04");
$d2 = ceil(($d1 - time()) / 60 / 60 / 24);
echo "There are " . $d2 ." days until 4th of July.";
?>
```

## PHP Include Files
The `include` and `require` statements insert content from one file into another.

### Difference Between `include` and `require`
- `require` causes a fatal error and stops execution if the file is missing.
- `include` only generates a warning and continues execution.

#### Syntax:
```php
include 'filename';
require 'filename';
```

#### Example:
```php
<?php include 'footer.php'; ?>
```

### PHP Include vs. Require Example
Using `include` (script continues even if file is missing):
```php
<?php include 'noFileExists.php';
echo "I have a $color $car.";
?>
```
Using `require` (script stops if file is missing):
```php
<?php require 'noFileExists.php';
echo "I have a $color $car.";
?>
```

## PHP File Handling
### PHP `readfile()` Function
The `readfile()` function reads a file and writes it to the output buffer.
```php
<?php
echo readfile("webdictionary.txt");
?>
```

### PHP Create File - `fopen()`
The `fopen()` function creates or opens a file.
```php
$myfile = fopen("testfile.txt", "w");
```

### PHP Write to File - `fwrite()`
```php
<?php
$myfile = fopen("newfile.txt", "w") or die("Unable to open file!");
$txt = "John Doe\n";
fwrite($myfile, $txt);
$txt = "Jane Doe\n";
fwrite($myfile, $txt);
fclose($myfile);
?>
```

### PHP Append Text
Appending text to an existing file:
```php
<?php
$myfile = fopen("newfile.txt", "a") or die("Unable to open file!");
$txt = "Donald Duck\n";
fwrite($myfile, $txt);
$txt = "Goofy Goof\n";
fwrite($myfile, $txt);
fclose($myfile);
?>
```

## PHP File Upload
### Configure `php.ini`
Ensure `file_uploads` is enabled:
```ini
file_uploads = On
```

### Create an HTML Form
```html
<form action="upload.php" method="post" enctype="multipart/form-data">
  Select image to upload:
  <input type="file" name="fileToUpload" id="fileToUpload">
  <input type="submit" value="Upload Image" name="submit">
</form>
```

### Create `upload.php`
```php
<?php
$target_dir = "uploads/";
$target_file = $target_dir . basename($_FILES["fileToUpload"]["name"]);
$uploadOk = 1;
$imageFileType = strtolower(pathinfo($target_file, PATHINFO_EXTENSION));

if (isset($_POST["submit"])) {
  $check = getimagesize($_FILES["fileToUpload"]["tmp_name"]);
  if ($check !== false) {
    echo "File is an image - " . $check["mime"] . ".";
    $uploadOk = 1;
  } else {
    echo "File is not an image.";
    $uploadOk = 0;
  }
}
?>
```









