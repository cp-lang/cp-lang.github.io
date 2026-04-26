# Data Structures

Data structures allow you to organize and store data efficiently. Flexa provides built-in support for arrays and structs, which are essential for managing collections of data and creating custom types. In this section, we'll explore how to use these data structures effectively.

---

## Arrays

Arrays are collections of elements of the same type. They are useful for storing and manipulating sequences of data.

### Declaring Arrays

Arrays are declared using the following syntax:

```flexa
var array_name: type[] = {element1, element2, ...};
```

- `array_name`: The name of the array.
- `type`: The type of elements in the array.
- `element1`, `element2`, ...: The initial elements of the array.

#### Example

```flexa
var numbers: int[] = {1, 2, 3, 4, 5};
var names: string[] = {"Alice", "Bob", "Charlie"};
```

### Declaring Array Size

Arrays can be defined with a fixed size using the following syntax:

```flexa
var numbers: int[5] = {1, 2, 3, 4, 5};
var names: string[3] = {"Alice", "Bob", "Charlie"};
```

### Initializing Fixed-Size Arrays

When an array has a fixed size (e.g. `int[10]`), you can initialize it in different ways:

| Syntax                          | Description                                            |
| ------------------------------- | ------------------------------------------------------ |
| `var arr: int[10];`             | Declares an array with 10 elements (all uninitialized) |
| `var arr: int[10] = {};`        | Initializes all positions with `null`                  |
| `var arr: int[10] = {0};`       | Initializes all positions with the value `0`           |
| `var arr: int[10] = {1,2,...};` | Initializes with explicit values per index             |

#### Example

```flexa
var empty: int[5] = {};       // All values are null
var zeros: int[5] = {0};      // All values are 0
var data: int[5] = {1,2,3,4,5}; // Explicit initialization
```

### Accessing Array Elements

Array elements are accessed using their index (starting from 0):

```flexa
var first_number = numbers[0]; // first_number = 1
var second_name = names[1];    // second_name = "Bob"
```

### Modifying Array Elements

You can modify array elements by assigning new values to specific indices:

```flexa
numbers[0] = 10; // numbers = {10, 2, 3, 4, 5}
```

### Array Length

The length of an array can be obtained using the `len` function:

```flexa
var count = len(numbers); // count = 5
```

### Iterating Over Arrays

You can use a `foreach` loop to iterate over the elements of an array:

```flexa
foreach (var num in numbers) {
  println("Number: " + num);
}
```

---

## Structs

Structs are user-defined types that group related data together. They are useful for creating complex data structures.

### Declaring Structs
Structs are declared using the `struct` keyword, followed by the struct name and a block of fields.

```flexa
struct StructName {
  var field1: type;
  var field2: type;
  ...
}
```

- `StructName`: The name of the struct.
- `field1`, `field2`, ...: The fields (variables) of the struct.

#### Example
```flexa
struct Person {
  var name: string;
  var age: int;
}
```

### Creating Struct Instances
You can create instances of a struct using the struct name followed by a block of field assignments.

```flexa
var person: Person = Person{name="Alice", age=30};
```

### Accessing Struct Fields
Struct fields are accessed using the dot (`.`) operator.

```flexa
println(person.name); // Prints "Alice"
println(person.age);  // Prints 30
```

### Modifying Struct Fields
You can modify struct fields by assigning new values.

```flexa
person.age = 31; // person.age is now 31
```

### Nested Structs
Structs can contain other structs as fields.

```flexa
struct Address {
  var street: string;
  var city: string;
}

struct Employee {
  var name: string;
  var address: Address;
}

var employee: Employee = Employee{
  name="Bob",
  address=Address{street="123 Main St", city="Springfield"}
}
```

Aqui está a seção atualizada com a nova informação sobre *unpacking* de variáveis `struct` em Flexa:

### Unpacking Struct Variables

In Flexa, variables of type `struct` can be *unpacked* directly into multiple variables using square brackets. This allows you to extract fields from a struct instance in a single line.

#### Syntax

```flexa
var [field1, field2, ...] = struct_variable;
```

Each variable on the left-hand side corresponds to the respective field in the struct, in the order they were declared in the struct definition.

#### Example

Given a struct:

```flexa
struct Person {
  name: string;
  age: int;
}
```

You can unpack an instance as follows:

```flexa
var person1 = Person("Alice", 30);
var [name, age] = person1;

println(name); // "Alice"
println(age);  // 30
```

This feature improves readability and reduces boilerplate when working with structured data.

### Iterating Over Structs
You can use a `foreach` loop to iterate over the key-value pairs of an struct.

```flexa
using flx.std.types;

foreach (entry: Pair in employee) {
  println(key + ": " + value);
}
```

Unpacked declarations can be used to get key-value entries too.

```flexa
foreach (var [key, value] in employee) {
  println(key + ": " + value);
}
```

---

## Array of Structs

You can create arrays of structs to manage collections of complex data.

```flexa
var people: Person[] = {
  Person{name="Alice", age=30},
  Person{name="Bob", age=25},
  Person{name="Charlie", age=35}
};

foreach (var person in people) {
  println(person.name + " is " + person.age + " years old.");
}
```

---

## What's Next?

Now that you understand how to work with arrays and structs, it's time to learn about **error handling** in Flexa. Head over to the [Error Handling](error-handling) section to dive deeper.

---

[← Back to Functions](functions) | [Next: Error Handling →](error-handling)
