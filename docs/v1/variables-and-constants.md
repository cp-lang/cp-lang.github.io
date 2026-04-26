# Variables and Constants

Variables and constants are fundamental building blocks in Flexa. They allow you to store and manipulate data throughout your program. In this section, we'll explore how to declare, initialize, and use variables and constants effectively.

---

## Variables

Variables are used to store data that can change during the execution of a program. In Flexa, variables are declared using the `var` keyword.

### Syntax

```flexa
var variable_name: type = value;
```

- `variable_name`: The name of the variable (must follow Flexa's identifier rules).
- `type`: The data type of the variable (optional if the type can be inferred).
- `value`: The initial value assigned to the variable (optional).

### Examples

```flexa
var age: int = 25;          // Explicitly typed variable
var name = "Alice";         // Type inferred as string
var is_active = true;       // Type inferred as bool
var price: float = 19.99;   // Explicitly typed variable
```

### Variable Scope

Variables in Flexa have block scope, meaning they are only accessible within the block where they are declared.

```flexa
<statement> {
  var x = 10; // x is only accessible within this block
  println(x); // Works fine
}
// println(x); // Error: x is out of scope
```

---

## Constants

Constants are used to store data that does not change during the execution of a program. In Flexa, constants are declared using the `const` keyword and must be initialized with a value.

### Syntax

```flexa
const constant_name: type = value;
```

- `constant_name`: The name of the constant (must follow Flexa's identifier rules).
- `type`: The data type of the constant (optional if the type can be inferred).
- `value`: The value assigned to the constant (required).

### Examples

```flexa
const PI: float = 3.14;     // Explicitly typed constant
const MAX_USERS = 100;      // Type inferred as int
const GREETING = "Hello!";  // Type inferred as string
```

### Constant Scope

Like variables, constants have block scope and are only accessible within the block where they are declared.

```flexa
<statement> {
  const TAX_RATE = 0.07; // TAX_RATE is only accessible within this block
  println(TAX_RATE);     // Works fine
}
// println(TAX_RATE); // Error: TAX_RATE is out of scope
```

---

## Variable and Constant Naming Rules

- Names must start with a letter or underscore (`_`).
- Names can contain letters, digits, and underscores.
- Names are case-sensitive (`myVar` and `myvar` are different).
- Reserved keywords (e.g., `var`, `const`, `fun`) cannot be used as names.

### Examples of Valid Names

```flexa
var myVar;
var _private_var;
var user123;
```

### Examples of Invalid Names

```flexa
var 123user;    // Cannot start with a digit
var my-var;     // Hyphens are not allowed
var var;        // Reserved keyword
```

---

## Best Practices

1. **Use Descriptive Names**: Choose meaningful names that describe the purpose of the variable or constant.

   ```flexa
   var user_age = 25;      // Good
   var ua = 25;            // Avoid
   ```

2. **Prefer Constants for Fixed Values**: Use `const` for values that do not change, as it makes your code more predictable and easier to understand.

   ```flexa
   const MAX_RETRIES = 3;  // Good
   var max_retries = 3;    // Avoid if the value is fixed
   ```

3. **Initialize Variables**: Always initialize variables when declaring them to avoid undefined behavior.
   ```flexa
   var count = 0;          // Good
   var count;              // Avoid (uninitialized)
   ```

---

## What's Next?

Now that you understand how to declare and use variables and constants, it's time to explore **control structures** like conditionals and loops. Head over to the [Control Structures](control-structures) section to learn more.

---

[← Back to Operators](operators) | [Next: Control Structures →](control-structures)
