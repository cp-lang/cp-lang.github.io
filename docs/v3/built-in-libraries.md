# Built-in Libraries

Flexa comes with a rich set of built-in libraries that provide essential functionality for common tasks such as file handling, networking, data manipulation, and more. These libraries are designed to make your development process faster and more efficient. In this section, we'll explore the available libraries and how to use them.

---

## Overview of Built-in Libraries

Here is a list of the main built-in libraries in Flexa:

1. **flx.core.console**: Provides functions for console control.
2. **flx.core.datetime**: Offers utilities for working with dates and times.
3. **flx.core.files**: Handles file operations like reading, writing, and managing files.
4. **flx.core.graphics**: Supports basic graphics operations (e.g., drawing shapes, rendering images).
5. **flx.core.HTTP**: Enables HTTP communication for web requests and APIs.
6. **flx.core.input**: Manages user input from devices like keyboards and mice.
7. **flx.core.sound**: Provides functionality for playing and manipulating audio.
8. **flx.std.collections.collection**: Implements common collection types (e.g., lists, sets).
9. **flx.std.collections.dictionary**: Supports key-value pair data structures.
10. **flx.std.collections.hashtable**: Implements hash tables for efficient data storage and retrieval.
11. **flx.std.collections.list**: Provides dynamic arrays and list operations.
12. **flx.std.collections.queue**: Implements queue data structures (FIFO).
13. **flx.std.collections.stack**: Implements stack data structures (LIFO).
14. **flx.std.DSL.FML**: Provides FML (Flexa Markup Language) parsing and serialization.
15. **flx.std.DSL.JSON**: Provides JSON parsing and serialization.
16. **flx.std.DSL.XML**: Provides XML parsing and serialization.
17. **flx.std.DSL.YAML**: Provides YAML parsing and serialization.
18. **flx.std.DSL.CSV**: Provides CSV parsing and serialization.
19. **flx.std.arrays**: Offers advanced array manipulation functions.
20. **flx.std.math**: Provides mathematical functions and constants.
21. **flx.std.print**: Enhances printing capabilities with formatting options.
22. **flx.std.random**: Implements random number generation and randomization utilities.
23. **flx.std.stopwatch**: Measures elapsed time for performance tracking.
24. **flx.std.strings**: Provides advanced string manipulation functions.
25. **flx.std.types**: Contais some useful struct types.
26. **flx.std.testing**: Offers tools for writing and running tests.
27. **flx.std.utils**: Includes miscellaneous utility functions.

---

## Using Built-in Libraries

To use a built-in library, you need to import it using the `using` keyword.

### Syntax
```flexa
using library_name;
```

### Example
```flexa
using flx.std.math;

println("The value of PI is: ", PI);
```

---

## Examples of Common Libraries

### 1. **flx.core.console**
This library provides functions for interacting with the console.

```flexa
using flx.core.console;

// Check if console is visible (it's always starts visible)
if (not is_console_visible()) {
  show_console(true) // If it's not, we set visible
}

// Sets background and foreground color
set_console_color(CL_WHITE, CL_LIGHT_BLUE);

println("This is a colored console!");
```

### 2. **flx.core.files**
This library handles file operations.

```flexa
using flx.core.files;

var f = open("example.txt", MODE_READ);  // Open a file in read mode
var content = read(f);                   // Reads the contents of a file
var fw = open("output.txt", MODE_WRITE); // Open a file in write mode
write(fw, content);                      // Writes content to a file
```

### 3. **flx.core.HTTP**
This library enables HTTP communication.

```flexa
using flx.core.HTTP;

include namespace flx;

// Sends an HTTP GET request to https://api.example.com/data
var response: HttpResponse = request(HttpRequest {
  hostname="api.example.com"
  path="data",
  method=GET
});
println(response.data);
```

### 4. **flx.std.math**
This library provides mathematical functions and constants.

```flexa
using flx.std.math;

println("Square root of 16: ", sqrt(16));
println("Value of PI: ", PI);
```

### 5. **flx.std.strings**
This library offers advanced string manipulation.

```flexa
using flx.std.strings;

var str = "Hello, Flexa!";
println("Uppercase: " + to_upper(str));
println("Lowercase: " + to_lower(str));
```

---

## Best Practices

1. **Import Only What You Need**: Import only the libraries you need to keep your code clean and efficient.
   ```flexa
   using flx.core.console; // Good
   using flx.core.*;       // Avoid (imports everything, which may be unnecessary)
   ```

2. **Explore Library Documentation**: Each library has its own documentation. Refer to it for detailed usage instructions.

3. **Use Libraries to Avoid Reinventing the Wheel**: Leverage built-in libraries to save time and effort.

---

## What's Next?

Now that you're familiar with the built-in libraries, it's time to explore the **built-in functions** provided by Flexa. Head over to the [Built-in Functions](built-in-functions) section to learn more.

---

[← Back to Error Handling](error-handling) | [Next: Built-in Functions →](built-in-functions)
