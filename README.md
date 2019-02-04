# PSR - Coding standard and coding style guide
[PSR-1 - Basic coding standard](https://github.com/php-fig/fig-standards/blob/master/accepted-1-basic-coding-standard.md?ref=LaravelCollections.com)  
[PSR-2 - Coding style guide](https://www.php-fig.org-2/?ref=LaravelCollections.com)  

## Table of content
1. PSR-1
    1. [General](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#general)
    2. [Namespace and Class names](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#namespace-and-class-names)
    3. Class Constants, Properties, and Methods
        1. [Constants](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#constants)
        2. [Properties](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#properties)
        3. [Methods](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#methods)
2. PSR-2
    1. General
        1. [Basic Coding Standard](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#basic-coding-standard)
        2. [Files](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#files)
        3. [Lines](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#lines)
        4. [Indenting](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#indenting)
        5. [Keywords and True/False/Null](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#keywords-and-truefalsenull)
    2. [Namespace and Use Declarations](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#namespace-and-use-declarations)
    3. Classes, Properties, and Methods
        1. [Extends and Implements](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#extends-and-implements)
        2. [Properties](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#properties-1)
        3. [Methods](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#methods-1)
        4. [Method Arguments](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#method-arguments)
        5. [abstract, final, and static](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#abstract-final-and-static)
        6. [Method and function call](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#method-and-function-calls)
    4. [Control Structures](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#control-structures)
        1. [if, elseif, else](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#if-elseif-else)
        2. [switch, case](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#switch-case)
        3. [while, do while](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#while-do-while)
        4. [for](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#for)
        5. [foreach](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#foreach)
        6. [try, catch](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#try-catch)
    5. [Closures](https://github.com/MichaelBecker2/PHP-Standards-Recommendations#closures)

## PSR-1
### General
* PHP code *must* use `<?php` or `<?=` tags
* PHP code *must* use only UTF-8 without BOM
* A PHP file *should* declare new symbols (classes, functions, constants, etc.) and cause no other side effects, or it *should* execute logic with side effects, but *should not* do both

### Namespace and Class names
* Each class is in a file by itself, and is in a namespace of at least one level: a top-level vendor name.
* Class names *must* be declared in `StudlyCase`
```php
<?php
namespace Vendor\Model;

class Foo
{
}
```

### Class Constants, Properties, and Methods
#### Constants
Class constants *must* be declared in all upper case with underscore separators
```php
<?php
namespace Vendor\Model;

class Foo
{
    const VERSION = '1.0';
    const DATE_APPROVED = '2012-06-01';
}
```

#### Properties
Whatever naming convention is used *should* be applied consistently within a reasonable scope.

#### Methods
Method names *must* be declared in `camelCase()`.

## PSR-2
### General
#### Basic Coding Standard
Code *must* follow all rules outlined in PSR-1.  

#### Files
* All PHP files *must* use the Unix LF (linefeed) line ending.
* All PHP files *must* end with a single blank line.
* The closing `?>` tag *must* be omitted from files containing only PHP.

#### Lines
* There *must not* be a hard limit on line length.
* The soft limit on line length *must* be 120 characters; automated style checkers *must* warn but *must not* error at the soft limit.
* Lines *should not* be longer than 80 characters; lines longer than that *should* be split into multiple subsequent lines of no more than 80 characters each.
* There *must not* be trailing whitespace at the end of non-blank lines.
* Blank lines *may* be added to improve readability and to indicate related blocks of code.
* There *must not* be more than one statement per line.

#### Indenting
Code *must* use an indent of 4 spaces, and *must not* use tabs for indenting.  

#### Keywords and True/False/Null
* PHP keywords *must* be in lower case.
* The PHP constants `true`, `false`, and `null` *must* be in lower case.

### Namespace and Use Declarations
* When present, there *must* be one blank line after the `namespace` declaration.
* When present, all `use` declarations *must* go after the `namespace` declaration.
* There *must* be one `use` keyword per declaration.
* There *must* be one blank line after the `use` block.
```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... additional PHP code ...

```

### Classes, Properties, and Methods
The term `class` refers to all classes, interfaces, and traits.

#### Extends and Implements
* The `extends` and `implements` keywords *must* be declared on the same line as the `class` name.
* The opening brace for the `class` *must* go on its own line; the closing brace for the `class` *must* go on the next line after the body.
```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // constants, properties, methods
}
```
Lists of `implements` *may* be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list *must* be on the next line, and there *must* be only one interface per line.
```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    // constants, properties, methods
}
```

#### Properties
* Visibility *must* be declared on all properties.
* The `var` keyword *must not* be used to declare a property.
* There *must not* be more than one property declared per statement.
* Property names *should not* be prefixed with a single underscore to indicate protected or private visibility.
```php
<?php
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
```

#### Methods
* Visibility *must* be declared on all methods.
* Method names *should not* be prefixed with a single underscore to indicate protected or private visibility.
* Method names *must not* be declared with a space after the method name. 
* The opening brace *must* go on its own line, and the closing brace *must* go on the next line following the body. 
* There *must not* be a space after the opening parenthesis, and there *must not* be a space before the closing parenthesis.
```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
```

#### Method Arguments
* In the argument list, there *must not* be a space before each comma, and there *must* be one space after each comma.
* Method arguments with default values *must* go at the end of the argument list.
```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function foo($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
```
* Argument lists *may* be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list *must* be on the next line, and there *must* be only one argument per line.
* When the argument list is split across multiple lines, the closing parenthesis and opening brace *must* be placed together on their own line with one space between them.
```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function aVeryLongMethodName(
        ClassTypeHint $arg1,
        $arg2,
        array $arg3 = []
    ) {
        // method body
    }
}
```

#### abstract, final, and static
* When present, the `abstract` and `final` declarations *must* precede the visibility declaration.
* When present, the `static` declaration *must* come after the visibility declaration.
```php
<?php
namespace Vendor\Package;

abstract class ClassName
{
    protected static $foo;

    abstract protected function zim();

    final public static function bar()
    {
        // method body
    }
}
```

#### Method and Function Calls
* When making a method or function call, there *must not* be a space between the method or function name and the opening parenthesis, there *must not* be a space after the opening parenthesis, and there *must not* be a space before the closing parenthesis. 
* In the argument list, there *must not* be a space before each comma, and there *must* be one space after each comma.
```php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
```
Argument lists *may* be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list *must* be on the next line, and there *must* be only one argument per line.
```php
<?php
$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
```

### Control Structures
* There *must* be one space after the control structure keyword
* There *must not* be a space after the opening parenthesis
* There *must not* be a space before the closing parenthesis
* There *must* be one space between the closing parenthesis and the opening brace
* The structure body *must* be indented once
* The closing brace *must* be on the next line after the body
The body of each structure *must* be enclosed by braces. This standardizes how the structures look, and reduces the likelihood of introducing errors as new lines get added to the body.

#### if, elseif, else
An `if` structure looks like the following. Note the placement of parentheses, spaces, and braces; and that `else` and `elseif` are on the same line as the closing brace from the earlier body.
```php
<?php
if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body;
}
```
The keyword `elseif` *should* be used instead of `else if` so that all control keywords look like single words.

#### switch, case
A `switch` structure looks like the following. Note the placement of parentheses, spaces, and braces. The `case` statement *must* be indented once from `switch`, and the `break` keyword (or other terminating keyword) *must* be indented at the same level as the `case` body. There *must* be a comment such as `// no break` when fall-through is intentional in a non-empty case body.
```php
<?php
switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Third case, return instead of break';
        return;
    default:
        echo 'Default case';
        break;
}
```

#### while, do while
A `while` statement looks like the following. Note the placement of parentheses, spaces, and braces.
```php
<?php
while ($expr) {
    // structure body
}
```
Similarly, a `do while` statement looks like the following. Note the placement of parentheses, spaces, and braces.
```php
<?php
do {
    // structure body;
} while ($expr);
```

#### for
A `for` statement looks like the following. Note the placement of parentheses, spaces, and braces.
```php
<?php
for ($i = 0; $i < 10; $i++) {
    // for body
}
```

#### foreach
A `foreach` statement looks like the following. Note the placement of parentheses, spaces, and braces.
```php
<?php
foreach ($iterable as $key => $value) {
    // foreach body
}
```

#### try, catch
A `try catch` block looks like the following. Note the placement of parentheses, spaces, and braces.
```php
<?php
try {
    // try body
} catch (FirstExceptionType $e) {
    // catch body
} catch (OtherExceptionType $e) {
    // catch body
}
```

### Closures
* Closures *must* be declared with a space after the function keyword, and a space before and after the use keyword.
* The opening brace *must* go on the same line, and the closing brace *must* go on the next line following the body.
* There *must not* be a space after the opening parenthesis of the argument list or variable list, and there *must not* be a space before the closing parenthesis of the argument list or variable list.
* In the argument list and variable list, there *must not* be a space before each comma, and there *must* be one space after each comma.
* Closure arguments with default values *must* go at the end of the argument list.
```php
<?php
$closureWithArgs = function ($arg1, $arg2) {
    // body
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // body
};
```
* Argument lists and variable lists *may* be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list *must* be on the next line, and there *must* be only one argument or variable per line.
* When the ending list (whether of arguments or variables) is split across multiple lines, the closing parenthesis and opening brace *must* be placed together on their own line with one space between them.
```php
<?php
$longArgs_noVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) {
    // body
};

$noArgs_longVars = function () use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // body
};

$longArgs_longVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // body
};

$longArgs_shortVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use ($var1) {
    // body
};

$shortArgs_longVars = function ($arg) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
    // body
};
```
Note that the formatting rules also apply when the closure is used directly in a function or method call as an argument.
```php
<?php
$foo->bar(
    $arg1,
    function ($arg2) use ($var1) {
        // body
    },
    $arg3
);
```
