# Error Handling

Error handling is a critical aspect of writing robust and reliable programs. Flexa provides mechanisms to handle errors and exceptions gracefully using `try-catch` blocks and the `throw` statement. In this section, we'll explore how to use these features effectively.

---

## Try-Catch Blocks

The `try-catch` block allows you to handle exceptions that may occur during the execution of your code. If an exception is thrown in the `try` block, the corresponding `catch` block will execute.

### Syntax
```flexa
try {
  // Code that may throw an exception
} catch (error) {
  // Code to handle the exception
}
```

- `try`: The block of code where exceptions are monitored.
- `catch`: The block of code that handles the exception. The `error` variable holds the exception object.

### Example
```flexa
using flx.std.types;

try {
  var result = 10 / 0; // This will throw a division by zero error
} catch (error: flx::Exception) {
  println("An error occurred: " + error);
}
```

---

## Throwing Exceptions

You can throw exceptions using the `throw` statement. This is useful for signaling errors or invalid states in your program.

### Syntax
```flexa
throw expression;
```

- `expression`: The exception object or value to throw.

### Example
```flexa
using flx.std.types;

include namespace flx;

fun divide(a: int, b: int): int {
    if (b == 0) {
      throw std::Exception{error="Division by zero is not allowed.", code=1};
    }
    return a / b;
}

try {
  var result = divide(10, 0);
} catch (ex) {
  println("Error: " + ex.error); // Prints "Error: Division by zero is not allowed."
}
```

Bare strings can be used to throw exceptions too:

```flexa
throw "Generating a default exception.";
```

---

## Unpacking Exceptions

You can unpack exceptions into variables to access specific properties or details.

### Example
```flexa
try {
  throw Exception{error="An error occurred", code=500};
} catch ([error, code]) {
  println("Error Code: " + code); // Prints "Error Code: 500"
  println("Error Message: " + error); // Prints "Error Message: An error occurred"
}
```

---

## Ignoring Errors

If you want to ignore errors, you can use `...` in the `catch` block. This is useful when you don't need to handle the error explicitly.

### Example
```flexa
try {
  var result = 10 / 0;
} catch (...) {
  println("An error occurred, but it was ignored.");
}
```

---

## Best Practices

1. **Handle Errors Gracefully**: Always handle exceptions to prevent your program from crashing unexpectedly.
   ```flexa
   try {
     risky_operation();
   } catch ([error, code]) {
     println("Operation failed: " + error);
   }
   ```

2. **Avoid Empty Catch Blocks**: Avoid catching exceptions without handling them, as this can hide bugs.
   ```flexa
   // Bad practice
   try {
      risky_operation();
   } catch (...) {
     // Do nothing
   }
   ```

3. **Log Errors**: Log errors for debugging and monitoring purposes.
   ```flexa
   try {
     risky_operation();
   } catch (var error) {
     log_error(error);
   }
   ```

---

## What's Next?

Now that you understand how to handle errors in Flexa, it's time to explore the **built-in libraries** that come with the language. Head over to the [Built-in Libraries](built-in-libraries) section to learn more.

---

[← Back to Data Structures](data-structures) | [Next: Built-in Libraries →](built-in-libraries)
