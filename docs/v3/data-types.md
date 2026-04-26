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
     var is_inactive: bool = false;
     ```

### 2. **Byte (`byte`)**
   - Represents 8 bit data, from 0 to 255 or characters (eg. `'A'`).
   - Example:
     ```flexa
     var grade: byte = 'A';
     var b: byte = 255;
     var bo: byte = 0o377;
     var bx: byte = 0xFF;
     var bb: byte = 0b11111111;
     var bd: byte = 0d255;
     var bytes: byte[10] = [0, 1, 2, 4, 8, 16, 32, 64, 128, 255];
     ```

### 3. **Integer (`int`)**
   - Represents whole numbers (e.g., `42`, `-7`), with no max size.
   - Example:
     ```flexa
     var age: int = 25;
     var i: int = 25;
     var io: int = 0o31;
     var ix: int = 0x19;
     var ib: int = 0b11001;
     var id: int = 0d25;
     ```

### 4. **Floating-Point (`float`)**
   - Represents decimal (64 bits precision) numbers (e.g., `3.14`, `-0.001`).
   - Example:
     ```flexa
     var pi: float = 3.1415;
     var em1 = 10e-1;
     var em0 = 10e-0;
     var e0 = 10e0;
     var ep0 = 10e+0;
     var e1 = 10e1;
     var ep1 = 10e+1;
     ```

### 5. **String (`string`)**
   - Represents a sequence of characters (e.g., `"Hello, Flexa!"`).
   - Example:
     ```flexa
     var message: string = "Welcome to Flexa!";
	 var multiline_string = `
	 This is a multiline string!
	 We can also have interpolated expressions by using \${}.
	 So we can say: ${message}
	 `;
     ```

---

## Composite Types

Composite types are used to group multiple values together. They include:

### 1. **Arrays**
   - Represents a fast size fixed collection of elements.
   - Example:
     ```flexa
     var size: int = int(read("Array size: "));
     var numbers: int[size];
     var matrix: int[3][3];
     ```

### 1. **Lits**
   - Represents a collection of elements of the same type.
   - Example:
     ```flexa
     var numbers: list = [1, 2, 3, 4, 5];
     var matrix: list = [[1, 2, 3], [1, 2, 3], [1, 2, 3]];
     ```
     ```

### 1. **Dictionaries**
   - Represents a collection of elements of the same type.
   - Example:
     ```flexa
     var foo: dict = {foo: "bar"};
     var bar: list = {% raw %}{"fux":{foo: "bar"}, qux:{foo: "bar"}}{% endraw %};
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
     var person2: struct Person; // classes has precedence when identifing a type, so it's possible to disambiguity by using struct before struct type in case of has both struct and class with same name
     ```

### 2. **Classes**
   - Represents a user-defined object that has it's variables and methods.
   - Example:
     ```flexa
     class Car {
       var name: string;
       var model: string;
       init(name, model) {
        self.name = name;
        self.model = model;
       }
       fun drive() {
        return "driving";
       }
     };

     var car: Car = Car("Gurgel", "Itaipu");
     var car2: class Car;
     ```

---

## Special Types

Flexa also supports special types for specific use cases:

### 1. **Function (`function`)**
   - Represents a function or lambda.
   - Example:
     ```flexa
     var greet: function = lambda (name: string) {
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
