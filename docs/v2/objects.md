# Classes

Classes are user-defined types that combine **data (fields)** and **behavior (methods)** into a single unit. They are used to model more complex concepts than basic data structures, encapsulating state, behavior, and access control.

In Flexa, classes are designed to be **explicit, structured, and readable**, using **definition scopes** instead of modifier-heavy syntax.

---

## Class Declaration

A class in Flexa is declared using the `class` keyword followed by its name and a body.

```flexa
class ClassName {
	// Class body
}
```

### Example

```flexa
class Person {
	var name: string;
	var age: int;
}
```

---

## Fields (Instance Members)

Fields declared directly inside a class are **instance members by default**. Each instance of the class has its own copy of these fields.

```flexa
class Point {
	var x: int;
	var y: int;
}
```

### Initial Values

Fields may be initialized at declaration time:

```flexa
class Counter {
	var value = 0;
}
```

---

## Constants in Classes

Classes support constants using the `const` keyword.

### Instance Constants

Instance constants must be initialized during object creation or in the initializer and **cannot be modified afterward**.

```flexa
class UserId {
	const value: string;

	init(value: string) {
		self.value = value;
	}
}
```

---

## Initializers (`init`)

An initializer defines how a class instance is created. It is automatically called when a new object is instantiated.

```flexa
class Person {
	var name: string;
	var age: int;

	init(name: string, age: int) {
		self.name = name;
		self.age = age;
	}
}
```

### Notes

- A class may define **one or more** initializers.
- `init` always operates in an **instance context**.
- `init` cannot be declared as `static`.

---

## Definition Scopes

Instead of using multiple modifiers per member, Flexa uses **definition scopes** to declare **visibility** and **allocation context**.

### Visibility Scopes

- `public` – accessible from anywhere
- `protected` – accessible within the class and subclasses
- `private` – accessible only inside the class

### Allocation Scopes

- `instance` – per object (default)
- `static` – associated with the class itself

---

## Scope Blocks

Scopes are defined using blocks inside the class body.

```flexa
class Example {

public {
	var x: int;
	fun getX() {
		return x;
	}
}

private {
	var secret: int = 42;
}

}
```

### Default Behavior

If no scope block is specified, members are considered:

- `instance`
- `private`

---

## Static Members

Static members belong to the class itself, not to individual instances.

```flexa
class MathUtils {

static public {
	const PI = 3.14159;

	fun square(x: float): float {
		return x * x;
	}
}

}
```

### Notes

- Static members **do not have access to `self`**
- Static methods can only access other static members

---

## Methods

Methods are functions defined inside a class. They can be instance or static methods depending on the scope block they are declared in.

### Instance Method Example

```flexa
class Greeter {

public {
	fun greet(name: string) {
		println("Hello, " + name);
	}
}
}
```

### Static Method Example

```flexa
class Logger {

static public {
	fun log(message: string) {
	println("[LOG] " + message);
	}
}

}
```

---

## Accessing Members

### Instance Members

```flexa
var p = Person("Alice", 30);
println(p.name);
```

### Static Members

```flexa
println(MathUtils.PI);
MathUtils.square(5);
```

---

## Inheritance

Flexa supports inheritance, a class may extend another class:

```flexa
class Animal {
  fun speak() {
    println("...");
  }
}

class Dog extends Animal {
  fun speak() {
    println("Woof!");
  }
}
```

TODO: traits and interfaces

---

## Encapsulation and Best Practices

1. **Prefer private fields**

   ```flexa
   private {
     var balance: float;
   }
   ```

2. **Expose behavior, not data**

   ```flexa
   public {
     fun deposit(amount: float) {
       balance += amount;
     }
   }
   ```

3. **Use static members for shared state or utilities**

   ```flexa
   static public {
     const VERSION = "1.0";
   }
   ```

4. **Avoid complex logic in initializers** Keep `init` focused on assigning fields.

---

## Common Errors

### Using `self` in static context

```flexa
static {
  fun broken() {
    println(self.x); // Error
  }
}
```

### Accessing private members from outside

```flexa
println(obj.secret); // Error
```

---

## What's Next?

Now that you understand how to work with classes, you can explore how they interact with **data structures**, **error handling**, and **larger application design**.

---

[← Back to Functions](functions) | [Next: Data Structures →](data-structures)
