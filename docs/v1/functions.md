# Functions

Functions are reusable blocks of code that perform a specific task. They are essential for organizing and modularizing your code. In Flexa, functions are declared using the `fun` keyword. This section will cover how to define, call, and use functions effectively.

---

## Function Declaration

A function in Flexa is declared using the following syntax:

```flexa
fun function_name(parameter1: type, parameter2: type, ...): return_type {
  // Function body
}
```

- `function_name`: The name of the function (must follow Flexa's identifier rules).
- `parameter1`, `parameter2`, ...: The input parameters (optional).
- `return_type`: The type of value the function returns (use `void` if the function does not return anything).
- `function body`: The code that executes when the function is called.

### Example
```flexa
fun greet(name: string): void {
  println("Hello, " + name + "!");
}
```

### 📝 Notes

* **Specifying parameter and return types is not mandatory**.
* **If the return type is not specified but the function contains a `return` statement, the return type is inferred as `any`**.

#### Example

```flexa
fun greet(name: string): void {
  println("Hello, " + name + "!");
}
```

Or without explicit types:

```flexa
fun greet(name) {
  println("Hello, " + name + "!");
}
```

And with implicit return type:

```flexa
fun sum(a, b) {
  return a + b; // the function type will be inferred as `any`
}
```

---

## Calling Functions

To call a function, use its name followed by parentheses `()` and any required arguments.

```flexa
function_name(argument1, argument2, ...);
```

### Example
```flexa
greet("Alice"); // Calls the greet function with "Alice" as the argument
```

---

## Parameters and Arguments

Functions can accept parameters, which are variables that hold the values passed to the function when it is called.

### Example with Parameters
```flexa
fun add(a: int, b: int): int {
  return a + b;
}

var result = add(5, 10); // result = 15
```

### Default Parameters
You can provide default values for parameters, which are used if no argument is passed.

```flexa
fun greet(name: string = "Guest"): void {
  println("Hello, " + name + "!");
}

greet();          // Prints "Hello, Guest!"
greet("Alice");   // Prints "Hello, Alice!"
```

---

### Rest Parameters
Functions can have rest parameters, which are used to receive a undefined number of parameters.

```flexa
fun max(...values): float {
  if (len(values) == 0) {
    return null;
  }

  var greater: float = values[0];

  foreach (var val: float in values) {
    greater = val > greater ? val : greater;
  }

  return greater;
}

println(max(1, 2, 3));
```

---

## Return Values

Functions can return a value using the `return` statement. The return type must match the declared return type of the function.

### Example
```flexa
fun square(x: int): int {
  return x * x;
}

var result = square(5); // result = 25
```

If a function does not return a value, its return type should be `void`.

```flexa
fun say_hello(): void {
  println("Hello!");
}
```

---

## Function Scope

Variables declared inside a function are local to that function and cannot be accessed outside of it.

```flexa
fun example(): void {
  var x = 10; // x is local to the example function
  println(x); // Works fine
}

// println(x); // Error: x is out of scope
```

---

## Anonymous Functions (Lambdas)

Flexa supports anonymous functions, also known as lambdas. These are functions without a name that can be assigned to variables or passed as arguments.

### Syntax
```flexa
var lambda_name: function = lambda (parameters): return_type {
  // Function body
};
```

### Example
```flexa
var square: function = lambda (x: int): int {
  return x * x;
};

println(square(5)); // Prints 25
```

---

## Higher-Order Functions

Higher-order functions are functions that take other functions as parameters or return functions as results.

### Example
```flexa
fun apply_twice(func: function, x: int): int {
  return func(func(x));
}

var result = apply_twice(fun (x: int): int { return x + 1; }, 5); // result = 7
```

---

## Recursion

Functions in Flexa can call themselves, a technique known as recursion.

### Example
```flexa
fun factorial(n: int): int {
  if (n <= 1) {
    return 1;
  }
  return n * factorial(n - 1);
}

println(factorial(5)); // Prints 120
```

---

## Best Practices

1. **Use Descriptive Names**: Choose meaningful names for functions that describe their purpose.
   ```flexa
   fun calculate_area(width: float, height: float): float {
     return width * height;
   }
   ```

2. **Keep Functions Small**: Break down complex tasks into smaller, reusable functions.
   ```flexa
   fun validate_input(input: string): bool {
     return input != "";
   }
   ```

3. **Avoid Side Effects**: Functions should ideally not modify external state unless necessary.

---

## What's Next?

Now that you understand how to work with functions, it's time to explore **data structures** like arrays and structs. Head over to the [Data Structures](data-structures) section to learn more.

---

[← Back to Control Structures](control-structures) | [Next: Data Structures →](data-structures)
