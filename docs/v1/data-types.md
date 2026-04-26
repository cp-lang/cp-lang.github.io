# Data Types

Flexa is a statically-typed language, which means that every variable and expression has a type that is known at 'compile' time. Flexa supports a variety of data types, including primitive types, composite types, and special types. In this section, we'll explore these types in detail.

---

## Primitive Types

Primitive types are the basic building blocks of Flexa programs. They include:

### 1. **Boolean (`bool`)**
   - Represents a truth value: `true` or `false`.
   - Example:
     ```flexa
     var is_active: bool = true;
     ```

### 2. **Integer (`int`)**
   - Represents whole numbers (e.g., `42`, `-7`).
   - Example:
     ```flexa
     var age: int = 25;
     ```

### 3. **Floating-Point (`float`)**
   - Represents decimal numbers (e.g., `3.14`, `-0.001`).
   - Example:
     ```flexa
     var pi: float = 3.14;
     ```

### 4. **Character (`char`)**
   - Represents a single Unicode character (e.g., `'a'`, `'😊'`).
   - Example:
     ```flexa
     var grade: char = 'A';
     ```

### 5. **String (`string`)**
   - Represents a sequence of characters (e.g., `"Hello, Flexa!"`).
   - Example:
     ```flexa
     var message: string = "Welcome to Flexa!";
     ```

---

## Composite Types

Composite types are used to group multiple values together. They include:

### 1. **Arrays**
   - Represents a collection of elements of the same type.
   - Example:
     ```flexa
     var numbers: int[] = {1, 2, 3, 4, 5};
     var matrix: int[3][3] = {% raw %}{{1, 2, 3}, {1, 2, 3}, {1, 2, 3}}{% endraw %};
     ```

### 2. **Structs**
   - Represents a user-defined type that groups related data.
   - Example:
     ```flexa
     struct Person {
       var name: string;
       var age: int;
     };

     var person: Person = Person{name="Alice", age=30};
     ```

---

## Special Types

Flexa also supports special types for specific use cases:

### 1. **Function (`function`)**
   - Represents a function or lambda.
   - Example:
     ```flexa
     var greet: function = fun (name: string) {
       println("Hello, " + name + "!");
     };
     ```

### 2. **Void (`void`)**
   - Represents the absence of a value. Used as a return type for functions that do not return anything.
   - Example:
     ```flexa
     fun say_hello(): void {
       println("Hello!");
     }
     ```

### 3. **Any (`any`)**
   - Represents a value of any type. Use with caution, as it bypasses type safety.
   - Example:
     ```flexa
     var data: any = 42; // Can hold any type
     data = "Now I'm a string!";
     ```

---

## Type Inference

Flexa supports type inference, which means you don't always need to explicitly specify the type of a variable. The compiler can infer the type based on the assigned value. An inferred variable will always have the any type, wich means that will accepts values of any type.

```flexa
var x = 10;       // x is any, but it's value is inferred as int
var y = 3.14;     // y is any, but it's value is inferred as float
var z = "Flexa";  // z is any, but it's value is inferred as string
```

---

## Type Casting

Flexa allows you to explicitly convert values from one type to another using type casting.

```flexa
var a: int = 10;
var b: float = float(a); // Cast int to float
```

---

## What's Next?

Now that you understand the data types supported by Flexa, it's time to learn how to operate values. Head over to the [Operators](operators) section to dive deeper.

---

[← Back to Basic Syntax](basic-syntax) | [Next: Operators →](operators)
