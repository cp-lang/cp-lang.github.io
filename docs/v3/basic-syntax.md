# Basic Syntax

In this section, we'll explore the basic syntax of the Flexa language. You'll learn about namespaces, variables, comments, and the fundamental structure of a Flexa program.

---

## Comments

Flexa supports two types of comments:
1. **Single-line comments**: Start with `//` and continue to the end of the line.
2. **Multi-line comments**: Enclosed between `/*` and `*/`.

```flexa
// This is a single-line comment

/*
  This is a multi-line comment.
  It can span multiple lines.
*/
```

---

## Importing Libraries

To use external libraries or modules, Flexa provides the `using` keyword. This allows you to include functionality from other files or libraries.

```flexa
using flx.std.types; // Import the standard types library
using my_libraries.utils; // Import a custom library
```

You also can use wildcard semantic to import all modules (`.flx` files) in a folder:

```flexa
using my_libraries.*;
```

And finally, it is possible to import specifics declarations in a module using the following syntax:

```flexa
from custom_lib use Foo, Bar;
```

---

## Basic Program Structure

A Flexa program typically consists of:
1. **Library imports**.
2. **Function and variable declarations**.
3. **Executable code** (e.g., function calls).

Here's an example of a simple Flexa program:

```flexa
using flx.std.random;

fun main() {
  println("Hello, Flexa", "!".repeat("!", Random.randi_range(0, 3)));
}

fun main();
```

---

## Variables and Constants

### Variables
Variables are declared using the `var` keyword, followed by the variable name, an optional type, and an optional initial value.

```flexa
var x: int = 10; // Declare an integer variable
var y = 20;      // Type inference, y is declared as any and value is inferred as int
```

### Constants
Constants are declared using the `const` keyword and must be initialized with a value.

```flexa
const PI: float = 3.1415; // Declare a constant
```

---

## Basic Input and Output

Flexa provides built-in functions for basic input and output operations:
- `print(...args)`: Prints a message to the console without a newline.
- `println(...args)`: Prints a message to the console with a newline.
- `read(...args)`: Reads a line of input from the console.
- `readch()`: Reads a single character from the console.

```flexa
var name = read("Enter your name:");
println("Hello, " + name + "!");
var age = read("Enter your age:");
println("Yout age is ", age, "!");
```

---

## Code Blocks

Code blocks are enclosed in curly braces `{}` and are used to group multiple statements together. They are commonly used in functions, loops, and conditionals.

```flexa
{
  var a = 10;
  var b = 20;
  println(a + b);
}
```

---

## What's Next?

Now that you understand the basic syntax of Flexa, it's time to explore the different **data types** supported by the language. Head over to the [Data Types](data-types) section to learn more.

---

[← Back to Introduction](introduction) | [Next: Data Types →](data-types)
