# Coding Standards for PHP and JavaScript

## Table of Contents
 
1. [**Introduction**](#1-introduction)  
2. [**Files**](#2-files)
3. [**PHP Tags**](#3-php-tags)
4. [**Namespaces of PHP**](#4-namespaces)
	1. [Namespace Declaration](#1-namespace-declaration)
	2. [Namespace Name](#2-namespace-name)
	3. [Multiple Namespaces](#3-multiple-namespaces)
5. [**Comments**](#5-comments)
6. [**Includes of PHP**](#6-includes)
	1. [Include/Require Once](#1-includerequire-once)
	2. [Parenthesis](#2-parenthesis)
	3. [Purpose of Include](#3-purpose-of-include)
7. [**Indenting and Whitespace**](#7-indenting-and-whitespace)
8. [**Functions**](#8-functions)
9. [**Control Structures**](#9-control-structures)
10. [**Arrays**](#10-arrays-of-javascript)
11. [**Variables**](#11-variables)

<!-- ---------------------------------------------------------------------- -->


## 1. Introduction
Standardization has it is wide advantages on any bussiness. In software development industry, coding standanrds and following best practices are key int he field of software improvement.

Coding standards are specific procedures that can be defined for programming languages specifying methods,styles,..etc.Developvers should maintain following the these standanrds across the whole project, So we can feel that this project is written by one developer in one session.

To make perfect project following the coding standards is not easy at all, and require the whole team to invest time for outputting a well organized code sticking to coding standards.Also,many developers do not stick to this standards when there is a short span of time .

So let's dive into the world of standardization in coding PHP and Javascript and know more about the specifications and details of best practices.

<!-- ---------------------------------------------------------------------- -->

## 2. Files

This section describes the format and naming convention of PHP files.

### Character Encoding 

MUST be set to UTF-8 in both PHP and Javascript.

### File Name in PHP

1. **Letters** MUST be all lowercase
	* e.g. `autoloader.php`
2. **Words** MUST be separated with a hyphen
	* e.g. `app-config.php`

### File Name in Javascript
* Must be lower case and can include only (-) or (_) with an extention `.js`.

&#9650; [Files](#2-files)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 3. PHP Tags

We MUST use the long tag `<?php?>` or the short-echo `<?= ?>` , not the `<?` shorthand.This is the most portable way to include PHP code in different operating systems and set-ups.

**Example of PHP Opening and Closing Tags**

1. `<?php echo 'if you want to serve PHP code in XHTML or XML documents,use these tags'; ?>`

2.  You can use the short echo tag to `<?= 'print this string' ?>`.
    It's equivalent to `<?php echo 'print this string' ?>`.

3.  `<? echo 'this code is within short tags, but will only work '.'if short_open_tag is enabled'; ?>` , so avoid using them.

&#9650; [PHP Tags](#3-php-tags)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 4. Namespaces of PHP

This section describes how to use one or more namespaces and their naming convention.

1. [**Namespace declaration**](#1-namespace-declaration) 
2. [**Namespace name**](#2-namespace-name)
3. [**Multiple namespaces**](#3-multiple-namespaces)

<!-- ------------------------------ -->

### 1. Namespace Declaration

Namespaces and classes MUST follow an "autoloading" PSR: [PSR-0, PSR-4].

Namespace are declared using a `namespace`.the file contains namespace must declare it at the top of the file or before any other code except:
1. declare statement
2. spaces
3. comments.

Names starting with a backslash are not allowed as they are used as relative namespace expressions.

**Example #1 Declaring a single namespace**

<pre lang=php>
namespace MyProject;

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */ }

// EOF
 
</pre>

<!-- ------------------------------ -->

### 2. Namespace Name

Namespace name usually written in UpperCamelCase.

<!-- ------------------------------ -->

### 3. Multiple Namespaces

Multiple Namespaces are may be declared in the same file,but it is strongly discouraged as a coding practice to combine multiple namespaces into the same file. The primary use case is to combine multiple PHP scripts into the same file. There are 2 allowed syntax.

**Example #1 Declaring multiple namespaces, simple combination syntax**

<pre lang=php>
&lt;?php
namespace MyProject;

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */  }

namespace AnotherProject;

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */  }
?&gt
 
</pre>

This syntax is not recommended for combining namespaces into a single file. Instead it is recommended to use the alternate bracketed syntax.

**Example #2 Declaring multiple namespaces, bracketed syntax**

<pre lang=php>
&lt;?php
namespace MyProject {

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */  }
}

namespace AnotherProject {

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */  }
}
?&gt

</pre>

&#9650; [Namespaces](#3-namespaces)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 5. Comments

This section describes how comments should be formatted and used.

### 1. Single-line Comments in PHP

MUST use two forward slashes `//`.Use of `#` is discouraged.

**Example :**
<pre lang=php>
&lt;?php

// This is a comment

?&gt
 
</pre>

### 1. Use single line comments in Javascript

* Leave a space between the slashes and the comment.
* Start with a capital letter, but don't end it with a period.

#### &#10004; Correct

<pre lang=js>

// A single-line comment

</pre>

* If a comment doesn't start immediately after a new indentation level, add an empty line and then add the comment. 

* Also, put your comments on separate lines preceding the code they are referring to.

#### &#10004; Correct

<pre lang=js>

function checkout(goodsPrice, shipmentPrice, taxes) {

  // Calculate the total price

  const total = goodsPrice + shipmentPrice + taxes;

  // Create and append a new paragraph to the document

  const para = document.createElement("p");

  para.textContent = `Total price is ${total}`;

  document.body.appendChild(para);

}

</pre>

<!-- ------------------------------ -->

### 2. Multi-line Comments in PHP

Multi-line comments MUST use the block format.

**Example :**

<pre lang=php>
&lt;?php

/* 
  This is a multi-line 
  comment because it can
  span multiple lines 
 */

?&gt
 
</pre>

**Example : but here it is following Doc Comments (PHPDoc)**

<pre lang=php>
&lt;?php

/* 
 * This is a multi-line 
 * comment because it can
 * span multiple lines 
 */

?&gt
 
</pre>

### 2. Multi-line comments In Javascript

Short comments are usually better, so try to keep them in one line of 60–80 characters. If this is not possible, use `//` at the beginning of each line:

#### &#10004; Correct

<pre lang=js>

// This is an example of a multi-line comment.

// The imaginary function that follows has some unusual

// limitations that I want to call out.

// Limitation 1

// Limitation 2

</pre>

#### &#10006; Incorrect

<pre lang=js>

/* This is an example of a multi-line comment.

  The imaginary function that follows has some unusual

  limitations that I want to call out.

  Limitation 1

  Limitation 2 */

</pre>

<!-- ------------------------------ -->

### 3. Best Practices for Comments

1. **Clarity and Conciseness**: they must be clear,avoid ambuguity in your comment.
2. **Regular Updates**: Keep your comments updated as your code is updated to reflect the new improved parts.
3. **Descriptive Naming**:Well-named entities such as methods and variables will provide you with clear understanding of the code instead of excessive comments.


&#9650; [Comments](#5-comments)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 6. Includes of PHP

This section describes the format for including and requiring files.

### 1. Include/Require Once

Include_once/require_once are used. Either of them will ensure that the file is included once.

#### &#10004; Correct

<pre lang=php>
&lt;?php

include_once 'some-file.php';
require_once 'some-other-file.php';

?&gt
 
</pre>

**For file paths:**

Start the file path with `.`.

<pre lang=php>
&lt;?php

include_once ./includes/mymodule_formatting.inc;
require_once 'some-other-file.php';

?&gt
 
</pre>

**Note:** Include_once/require_once are statements not functions so you have to put parentheses around the file to be included

&#9650; [Includes](#6-includes)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 7. Indenting and Whitespace

### Indenting and Whitespace in PHP

1. Use an indent of 2 spaces, with no tabs.

2. Lines should have no trailing whitespace at the end.

3. Files should be formatted with \n as the line ending (Unix line endings), not \r\n (Windows line endings).

4. All text files should end in a single newline (\n).

5. All blocks at the beginning of a PHP file and separated by a blank line. This includes the block comment, the namespace declaration and the use statements as well as the subsequent code in the file. So, for example, a file header might look as follows: 

**Example:**

<pre lang=php>
&lt;?php

namespace ThisIsTheNamespace;

use Drupal\foo\Bar;

/**
 * Provides examples.
 */

class name {

</pre>

### Indenting and Whitespace in PHP

* No whitespace at the end of line or on blank lines.

* Lines should usually be no longer than 80 characters as long lines indicate disorganized code.

* Control Blocksif/else/for/while/try blocks should always use braces, and always go on multiple lines.

* Unary operators (e.g., ++, --) must not have space next to their operand.

* The ? and : in a ternary conditional must have space on both sides.

* No filler spaces in empty constructs (e.g., {}, [], fn()).

* function bodies are indented by one tab.

&#9650; [Indenting and Whitespace in PHP](#7-indenting-and-whitespace-in-php)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 8. Functions

This section describes the format for function names, calls and declarations.

###  Function Name in PHP

Function name should be all lowercase and words and separated by an underscore.

#### &#10006; Incorrect

<pre lang=php>
&lt;?php

get_Welcome_Message();
Get_Welcome_Message();
GET_WELCOME_MESSAGE();

// EOF
 
</pre>

&#8627; Incorrect because the function names are not all lowercase.

<pre lang=php>
&lt;?php

getwelcomemessage();

// EOF
 
</pre>

&#8627; Incorrect because `get`, `welcome` and `message` are not separated with an underscore.

#### &#10004; Correct

<pre lang=php>
&lt;?php

get_welcome_message();

// EOF
 
</pre>

###  Function name in Javascript

* Use LowerCamelCase characters, starting with a lowercase character.

#### &#10004; Correct

<pre lang=js>

function sayHello() {

  console.log("Hello!");

}

</pre>

#### &#10006; Incorrect

<pre lang=js>

function SayHello() {

  console.log("Hello!");

}

</pre>

<!-- ------------------------------ -->

### 2. Function Call

**Function Call:**

* Functions should be called with no spaces between the function name, the opening parenthesis, and the first parameter.
* Spaces between commas and each parameter, and no space between the last parameter, the closing parenthesis, and the semicolon.

**Example:**

`$var = foo($bar, $baz, $quux);`
* In cases of block related assignments you can add more space to increase readability.
**Example:**

<pre lang=php>
$short         = foo($bar);

$long_variable = foo($baz);

 </pre>

<!-- ------------------------------ -->

### 3. Function Declaration in PHP

* Argument list should be splitted on multiple lines and indented once
* The first argument in the list must be on the second line.
* The last argument in the list must use a trailing comma.
* The closing parenthesis and opening brace must be placed together on their own line with one space between them.

#### &#10004; Correct

<pre lang=php>
&lt;?php

function funstuff_system(

	string $foo,
	string $name,
	int $num,
) {
  // body
}

// EOF
 
</pre>


### 2. Function Declaration in Javascript

* Use the function declaration over function expressions to define functions.

#### &#10004; Correct 

<pre lang=js>

function sum(a, b) {

  return a + b;

}

</pre>

#### &#10006; Incorrect

<pre lang=js>

let sum = function (a, b) {

  return a + b;

};

</pre>

* When using a function passed to another function as a callback, if you do not need to access `this`, use an arrow function to make the code shorter and cleaner. 

#### &#10004; Correct

<pre lang=js>

const array1 = [1, 2, 3, 4];

const sum = array1.reduce((a, b) => a + b);

</pre>

#### &#10006; Incorrect

<pre lang=js>

const array1 = [1, 2, 3, 4];

const sum = array1.reduce(function (a, b) {

  return a + b;

});

</pre>

* Use function declarations with the keyword `function` instead of useing arrow functions for methods :

#### &#10004; Correct

<pre lang=js>

function x() {

  // …

}
</pre>

#### &#10006; Incorrect

<pre lang=js>

const x = () => {
  // …
};

</pre>

* In arrow functions, use implicit return (also known as expression body) when possible:

#### &#10004; Correct

<pre lang=js>

arr.map((e) => e.id);

</pre>

#### &#10006; Incorrect

<pre lang=js>

arr.map((e) => {

  return e.id;

});

</pre>

&#9650; [Functions](#8-functions)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 9. Control Structures

This section defines the layout and usage of control structures.

### 1. If, Elseif, Else in PHP
* `elseif` is used instead of `else if`
* `elseif` and `else` MUST be between `}` and `{` on one line
*  Spaces should be kept between control keyword and opening parenthesis.
*  opening braces should be on the same line as the opening statement, preceded by one space
*  The closing curly should be on a line by itself and indented to the same level as the opening statement.


#### &#10004; Correct

<pre lang=php>
&lt;?php

if (condition1 || condition2) {
  action1;
}
elseif (condition3 && condition4) {
  action2;
}
else {
  defaultaction;
}

// EOF
 
</pre>

### 1. If, Elseif, Else in Javascript

* If the if statement ends with a return, Continue right after the if statement insted of adding an else statement.

#### &#10004; Correct

<pre lang=js>

if (test) {

  // test is true

  return;

}

// test is false

</pre>

#### &#10006; Incorrect

<pre lang=js>

if (test) {

  // test is true
  
  return;

} else {

  // Perform something if test is false

}

</pre>

<!-- ------------------------------ -->

### 2. Switch statements in PHP

* Case statement MUST be indented once
* Case body MUST be indented twice
* Break keyword MUST be indented twice
* Case logic MUST be separated by one blank line

#### &#10004; Correct

<pre lang=php>
&lt;?php

switch (condition) {
  case 1:
    action1;
    break;

  case 2:
    action2;
    break;

  default:
    defaultaction;
}

// EOF
 
</pre>

### 3. Switch statements in Javascript

* Don't use break statement after return statement in a specific case as it will be unreachable.

#### &#10004; Correct

<pre lang=js>

switch (species) {

  case "chicken":

    return farm.shed;

  case "horse":

    return corral.entry;

  default:

    return "";

}

</pre>

#### &#10006; Incorrect

<pre lang=js>

switch (species) {

  case "chicken":
    return farm.shed;

    break;

  case "horse":

    return corral.entry;

    break;

  default:

    return "";

}

</pre>

* If you need to do that, add a comment explaining why.

* When you declare a variable for a case, you need to use braces to define a scope:

<pre lang=js>

switch (fruits) {

  case "Orange": {

    const slice = fruit.slice();

    eat(slice);

    break;

  }

  case "Apple": {

    const core = fruit.extractCore();

    recycle(core);

    break;
    
  }
}

</pre>

<!-- ------------------------------ -->

### 3. While, Do While in PHP

#### &#10004; Correct

<pre lang=php>
&lt;?php

while ($expr) {
	// structure body
}

do {
	// structure body;
} while ($expr);

// EOF
 
</pre>

&#9650; [Control Structures](#9-control-structures)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 10. Arrays

### PHP:

* Elements of the array should be separated by a comma then one space 

**Example:** 

`$array = ['hello', 'world', 'foo' => 'bar'];`

* if the line declaring an array is longer than 80 characters (often the case with form and menu declarations), elements should be splitted into multiple lines, and indented one level

**Example:** 

<pre lang=php>
&lt;?php

$form['title'] = [
	'#type' => 'textfield',
  	'#title' => t('Title'),
  	'#size' => 60,
  	'#maxlength' => 128,
  	'#description' => t('The title of your node.'),
];
 
</pre>

<!-- ---------------------------------------------------------------------- -->

###  JAVASCRIPT

* Arrays can be declared on a single line if they are short . When an array is too long to fit on one line, each member must be placed on its own line and each line ended by a comma.

**Example:**

<pre lang=js>

// Preferred
var obj = {
    ready: 9,
    when: 4,
    'you are': 15,
};
var arr = [
    9,
    4,
    15,
];

// Acceptable for small objects and arrays
var obj = { ready: 9, when: 4, 'you are': 15 };
var arr = [ 9, 4, 15 ];

// Bad
var obj = { ready: 9,
    when: 4, 'you are': 15 };
var arr = [ 9,
    4, 15 ];

</pre>

* Add extra spaces around elements and arguments:

**Example:**

`array = [ a, b ];`

* Arrays are created using the shorthand [] constructor instead of the new Array() or intialize it during construction.

#### &#10006; Incorrect

<pre lang=js>

const visitedCities = new Array(length);
 
</pre>


#### &#10004; Correct

<pre lang=js>

const visitedCities = [];
var myArray = [ 1, 'orange', 2, 'user' ];

</pre>

* Adding items to an array is done using `push()` and not direct assignment. 

#### &#10006; Incorrect

<pre lang=js>
 
pets[pets.length] = "cat";

</pre>

#### &#10004; Correct

<pre lang=js>

pets.push("cat");

</pre>

&#9650; [ Arrays ](#10-arrays)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 11. Variables 

### Variables naming in PHP

* Variables can start with ($) or (_) but not a series of special characters.

* Avoid using reserved keywords.

* Variables can contain number,characters or (_) not any special characters

* Use camelcase for letters.

* Choose variable names related to what they are reffering to.

#### &#10006; Incorrect

<pre lang=php>
&gt?php

hey ="not so"; //doesn't have $
$123buckle ="still wrong"; //cannot follow $ with a number
$@gmail ="ooops error!"; //cannot use @

</pre>

#### &#10004; Correct

<pre lang=php>

$manure = "growth supplements";
$_dressSize = 4;
$hymn123 = "my young days";

</pre>

### Variables naming in Javascript

* Use short identifiers, but avoid unknown abbreviations. For example, `apple` is better than `ale`

* For collections, avoid adding words as list, array in the name. Use content name in the plural form. For example, for an array of cars, use cars and not carArray or carList.

* For primitive values, use camelCase, starting with a lowercase character. Do not use (_). For example, use redCar rather than red_car.

* Avoid using articles and possessives. For example, use car instead of myCar or aCar. There may be exceptions, like when describing a feature in general without a practical context.

#### &#10004; Correct

<pre lang=js>

const playerScore = 0;
const speed = distance / time;

</pre>

#### &#10006; Incorrect

<pre lang=js>

const thisIsaveryLONGVariableThatRecordsPlayerscore345654 = 0;
const s = d / t;

</pre>

&#9650; [ Variables ](#11-arrays)

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

---

References:<br />
[Horde](http://www.horde.org/apps/horde/docs/CODING_STANDARDS), [Pear](http://pear.php.net/manual/en/standards.php), [PSR-1](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md), [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md), [Symfony](http://symfony.com/doc/current/contributing/code/standards.html), and [WordPress](http://make.wordpress.org/core/handbook/coding-standards/php/), [Google](https://google.github.io/styleguide/jsguide.html#source-file-basics), [MULTIDOTS](https://www.multidots.com/blog/importance-of-coding-standard-and-code-quality-in-software-development/#:~:text=Put%20simply%2C%20if%20coding%20standards,bugs%20and%20errors%20in%20logic.), [WordpressHandbook](https://infinum.com/handbook/wordpress/coding-standards/php-coding-standards/naming#file-naming),[PHP](https://www.php.net/manual/en/language.basic-syntax.comments.php), [backDrop](https://docs.backdropcms.org/php-standards#function-declarations), [educative](https://www.educative.io/answers/what-are-the-naming-conventions-of-variables-in-php)