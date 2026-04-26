# Built-in Functions

Flexa provides a set of built-in functions that are always available, regardless of which libraries you import. These functions cover common tasks like input/output, string and array manipulation, and system operations. In this section, we'll explore these functions and how to use them effectively.

---

## Overview of Built-in Functions

Here are the main built-in functions in Flexa:

1. **print**: Writes one or more values to the console without a newline.
2. **println**: Writes one or more values to the console followed by a newline.
3. **read**: Reads a line of input from the console; can optionally display one or more prompt messages.
4. **readch**: Reads a single character from the console; can also accept prompt messages.
5. **len**: Returns the length of a string or array.
6. **sleep**: Pauses the program for a specified number of milliseconds.
7. **system**: Executes a system command.

---

## Using Built-in Functions

### 1. **print**
The `print` function writes a message to the console without adding a newline at the end.

#### Syntax
```flexa
print(message);
```

#### Example
```flexa
print("Hello, ");
print("Flexa!");
// Output: Hello, Flexa!
```

### 2. **println**
The `println` function writes a message to the console and adds a newline at the end.

#### Syntax
```flexa
println(message);
```

#### Example
```flexa
println("Hello, Flexa!");
// Output: Hello, Flexa! (followed by a newline)
```

### 3. **read**
The `read` function reads a line of input from the console.

#### Syntax
```flexa
var input = read();
```

#### Example
```flexa
println("Enter your name:");
var name = read();
println("Hello, " + name + "!");
```

### 4. **readch**
The `readch` function reads a single character from the console.

#### Syntax
```flexa
var char = readch();
```

#### Example
```flexa
println("Press any key:");
var key = readch();
println("You pressed: ", key);
```

### 5. **len**
The `len` function returns the length of a string or array.

#### Syntax
```flexa
var length = len(value);
```

#### Example
```flexa
var str = "Hello, Flexa!";
var arr = {1, 2, 3, 4, 5};

println("Length of string: ", len(str)); // Output: 13
println("Length of array: ", len(arr));  // Output: 5
```

### 6. **sleep**
The `sleep` function pauses the program for a specified number of milliseconds.

#### Syntax
```flexa
sleep(milliseconds);
```

#### Example
```flexa
println("Starting in 3 seconds...");
sleep(3000); // Pause for 3 seconds
println("Go!");
```

### 7. **system**
The `system` function executes a system command.

#### Syntax
```flexa
var result = system(command);
```

#### Example
```flexa
var result = system("ls -l"); // Lists files in the current directory (Unix-based systems)
println(result);
```

---

## Input and Output with Multiple Parameters

The functions `print`, `println`, `read`, and `readch` in Flexa support **zero or more arguments**. This means you can pass any number of values to these functions, and they will automatically concatenate and format them.

This makes input and output highly flexible and convenient, especially for debugging or building dynamic messages.

### Examples

```flexa
println(); // Prints just a newline

println("Hello"); // Prints: Hello

println("Hello,", " ", "world!", 42); 
// Prints: Hello, world!42

var name = "John";
var age = 30;
print("Name: ", name, ", Age: ", age);
// Output: Name: John, Age: 30
```

```flexa
var key = readch("Press any key to continue...");
println("You pressed:", " ", key);
```

You can also use `read()` without arguments for a prompt-less input:

```flexa
var input = read(); // Waits for user input without printing anything

var response = read("Type something: ");
println("You typed:", response);
```

---

## Examples of Built-in Functions

### Example 1: Basic Input/Output
```flexa
println("What is your name?");
var name = read();
println("Hello, " + name + "!");

println("Press any key to exit...");
var key = readch();
println("You pressed: " + key);
```

### Example 2: Measuring Array Length
```flexa
var numbers = {1, 2, 3, 4, 5};
println("The array has ", len(numbers), " elements.");
```

### Example 3: Using `sleep` for Delays
```flexa
println("Starting countdown:");
for (var i = 5; i >= 1; i--) {
  println(i);
  sleep(1000); // Wait 1 second
}
println("Blast off!");
```

### Example 4: Executing System Commands
```flexa
println("Listing files in the current directory:");
var result = system("dir"); // Windows
// var result = system("ls -l"); // Unix-based systems
println(result);
```

---

## Best Practices

1. **Use `println` for Debugging**: Use `println` to print debug messages during development.
   ```flexa
   println("Debug: Current value = " + value);
   ```

2. **Validate Input**: Always validate input from the user to avoid unexpected behavior.
   ```flexa
   using flx.std.utils; // is_number

   var age = read();
   if (is_number(age)) {
     println("Your age is: ", age);
   } else {
     println("Invalid input. Please enter a number.");
   }
   ```

3. **Avoid Blocking Calls**: Use `sleep` judiciously to avoid blocking the program for too long.

4. **Handle System Command Output**: Be cautious when using `system`, as it executes commands directly on the operating system.

---

## What's Next?

Now that you're familiar with the built-in functions, it's time to explore **advanced examples** that combine multiple features of Flexa. Head over to the [Advanced Examples](advanced-examples) section to see Flexa in action.

---

[← Back to Built-in Libraries](built-in-libraries) | [Next: Advanced Examples →](advanced-examples)
