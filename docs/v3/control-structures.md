# Control Structures

Control structures allow you to control the flow of execution in your Flexa programs. They include conditionals, loops, and flow control statements. In this section, we'll explore how to use these structures effectively.

---

## Conditionals

Conditionals allow you to execute different blocks of code based on certain conditions.

### 1. **If Statement**

The `if` statement executes a block of code if a condition is true.

```flexa
if (condition) {
  // Code to execute if the condition is true
}
```

#### Example

```flexa
var age = 18;

if (age >= 18) {
  println("You are an adult.");
}
```

### 2. **If-Else Statement**

The `if-else` statement allows you to execute one block of code if a condition is true and another block if it is false.

```flexa
if (condition) {
  // Code to execute if the condition is true
} else {
  // Code to execute if the condition is false
}
```

#### Example

```flexa
var age = 16;

if (age >= 18) {
  println("You are an adult.");
} else {
  println("You are a minor.");
}
```

### 3. **Else-If Statement**

The `else-if` statement allows you to check multiple conditions.

```flexa
if (condition1) {
  // Code to execute if condition1 is true
} else if (condition2) {
  // Code to execute if condition2 is true
} else {
  // Code to execute if all conditions are false
}
```

#### Example

```flexa
var score = 85;

if (score >= 90) {
  println("Grade: A");
} else if (score >= 80) {
  println("Grade: B");
} else if (score >= 70) {
  println("Grade: C");
} else {
  println("Grade: F");
}
```

### 4. **Switch Statement**

The `switch` statement allows you to execute different blocks of code based on the value of an expression.

```flexa
switch (expression) {
  case value1:
    // Code to execute if expression == value1
    break;
  case value2:
    // Code to execute if expression == value2
    break;
  default:
    // Code to execute if no case matches
}
```

#### Example

```flexa
var day = 3;

switch (day) {
  case 1:
    println("Monday");
    break;
  case 2:
    println("Tuesday");
    break;
  case 3:
    println("Wednesday");
    break;
  default:
    println("Invalid day");
}
```

---

## Loops

Loops allow you to execute a block of code repeatedly.

### 1. **While Loop**

The `while` loop executes a block of code as long as a condition is true.

```flexa
while (condition) {
  // Code to execute while the condition is true
}
```

#### Example

```flexa
var i = 0;

while (i < 5) {
  println("i = " + i);
  i++;
}
```

### 2. **Do-While Loop**

The `do-while` loop executes a block of code at least once, then repeats as long as a condition is true.

```flexa
do {
  // Code to execute at least once
} while (condition);
```

#### Example

```flexa
var i = 0;

do {
  println("i = " + i);
  i++;
} while (i < 5);
```

### 3. **For Loop**

The `for` loop allows you to execute a block of code a specific number of times.

```flexa
for (expression1; expression2; expression3) {
  // Code to execute in each iteration
}
```

- Expression 1 is executed (one time) before the execution of the code block.
- Expression 2 defines the condition for executing the code block.
- Expression 3 is executed (every time) after the code block has been executed.

#### Example

```flexa
for (var i = 0; i < 5; i++) {
  println("i = " + i);
}
```

### 4. **Foreach Loop**

The `foreach` loop iterates over elements in a collection (e.g., arrays, strings, structs).

```flexa
foreach (var element in collection) {
  // Code to execute for each element
}
```

#### Example

```flexa
var numbers = {1, 2, 3, 4, 5};

foreach (var num in numbers) {
  println("Number: " + num);
}
```

---

## Flow Control

Flow control statements allow you to alter the flow of execution in loops and functions.

### 1. **Break Statement**

The `break` statement exits a loop or `switch` statement immediately.

```flexa
while (true) {
  if (condition) {
    break; // Exit the loop
  }
}
```

#### Example

```flexa
for (var i = 0; i < 10; i++) {
  if (i == 5) {
    break; // Exit the loop when i == 5
  }
  println("i = " + i);
}
```

### 2. **Continue Statement**

The `continue` statement skips the rest of the current iteration and moves to the next iteration of the loop.

```flexa
for (var i = 0; i < 10; i++) {
  if (i % 2 == 0) {
    continue; // Skip even numbers
  }
  println("i = " + i);
}
```

### 3. **Return Statement**

The `return` statement exits a function and optionally returns a value.

```flexa
fun add(a: int, b: int): int {
  return a + b;
}
```

---

## What's Next?

Now that you understand control structures, it's time to learn about **functions** in Flexa. Head over to the [Functions](functions) section to dive deeper.

---

[← Back to Variables and Constants](variables-and-constants) | [Next: Functions →](functions)
