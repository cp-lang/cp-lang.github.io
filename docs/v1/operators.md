# Operators

Operators in Flexa are special symbols or keywords used to perform operations on values and variables. They are categorized by their functionality, such as arithmetic, logical, or assignment operations.

This page provides a concise reference to all operators available in the Flexa language.

---

## Arithmetic Operators

These operators perform basic mathematical operations:

| Operator | Description                     |
| -------- | ------------------------------- |
| `+`      | Addition                        |
| `-`      | Subtraction                     |
| `*`      | Multiplication                  |
| `/`      | Division                        |
| `%`      | Modulo (remainder)              |
| `**`     | Exponentiation (power)          |
| `/%`     | Floor division (integer result) |

---

## Comparison Operators

Used to compare values. These expressions return a boolean result:

| Operator | Description                                                                                  |
| -------- | -------------------------------------------------------------------------------------------- |
| `==`     | Equal                                                                                        |
| `!=`     | Not equal                                                                                    |
| `<`      | Less than                                                                                    |
| `>`      | Greater than                                                                                 |
| `<=`     | Less than or equal                                                                           |
| `>=`     | Greater than or equal                                                                        |
| `<=>`    | Three-way comparison. Returns:<br>• `-1` if left < right<br>• `0` if equal<br>• `1` if left > right |

---

## Logical Operators

Used for boolean logic:

| Operator | Description |
| -------- | ----------- |
| `and`    | Logical AND |
| `or`     | Logical OR  |
| `not`    | Logical NOT |

---

## Bitwise Operators

Operate directly on binary representations of integers:

| Operator | Description |
| -------- | ----------- |
| `&`      | Bitwise AND |
| `\|`     | Bitwise OR  |
| `^`      | Bitwise XOR |
| `~`      | Bitwise NOT |
| `<<`     | Left shift  |
| `>>`     | Right shift |

---

## Assignment Operators

Used to assign values to variables:

| Operator | Description            |
| -------- | ---------------------- |
| `=`      | Simple assignment      |
| `+=`     | Add and assign         |
| `-=`     | Subtract and assign    |
| `*=`     | Multiply and assign    |
| `/=`     | Divide and assign      |
| `%=`     | Modulo and assign      |
| `/%=`    | Floor division and assign |
| `**=`    | Power and assign       |
| `&=`     | Bitwise AND and assign |
| `\|=`    | Bitwise OR and assign  |
| `^=`     | Bitwise XOR and assign |
| `<<=`    | Left shift and assign  |
| `>>=`    | Right shift and assign |

---

## Increment and Decrement

Shorthand for increasing or decreasing a value:

| Operator | Description    |
| -------- | -------------- |
| `++`     | Increment by 1 |
| `--`     | Decrement by 1 |

---

## Value Reference Operators

Used for referencing and dereferencing variables:

| Operator | Description                           |
| -------- | ------------------------------------- |
| `ref`    | Get the original reference of a value |
| `unref`  | Get a copy of a value                 |

**Note:** struct type values are referenced by default.

---

## Type and Introspection Operators

Useful for inspecting or identifying values at runtime:

| Operator       | Description                                     |
| -------------- | ----------------------------------------------- |
| `typeof(x)`    | Returns the type name of `x` as a string e.g. `"int"`, `"bool"`, `"string"`, `"MyStruct"` |
| `typeid(x)`    | Returns a unique integer ID for the type of `x` |
| `refid(x)`     | Returns the reference ID of an object or array (useful to check if two references point to the same entity) |
| `is_struct(x)` | Returns `true` if `x` is a struct instance      |
| `is_array(x)`  | Returns `true` if `x` is an array               |
| `is_any(x)`    | Returns `true` if `x` is of type `any`          |

---

## Ternary Operator

Shorthand conditional expression:

```flexa
condition ? expression_if_true : expression_if_false
```

Example:

```flexa
var result = age >= 18 ? "adult" : "minor";
```

---

## What's Next?

Now that you understand the data types supported by Flexa, it's time to learn how to declare and use **variables and constants**. Head over to the [Variables and Constants](variables-and-constants) section to dive deeper.

---

[← Back to Data Types](data-types) | [Next: Variables and Constants →](variables-and-constants)
