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


