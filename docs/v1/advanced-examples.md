# Advanced Examples

In this section, we'll explore advanced examples that demonstrate the power and flexibility of the Flexa programming language. These examples combine multiple features of Flexa, such as functions, control structures, data manipulation, and built-in libraries, to solve real-world problems.

---

## Example 1: File Processing

This example reads a file, processes its contents, and writes the results to a new file.

```flexa
using flx.core.files;
using flx.std.strings;
using flx.std.structs;

include namespace flx;

fun process_file(input_file: string, output_file: string): void {
  try {
    var file = open(input_file, MODE_READ);
    var content = read(file);
    var lines = split(content, "\n");

    var processed_lines: string[] = {};
    foreach (var i = 0; i < len(lines); i++) {
      var trimmed_line = trim(line);
      if (trimmed_line != "") {
        processed_lines += {trimmed_line};
      }
    }

    write_file(output_file, join(processed_lines, "\n"));
    println("File processed successfully.");
  } catch (var error) {
    println("Error processing file: " + error);
  }
}

process_file("input.txt", "output.txt");
```

---

## Example 2: HTTP API Client

This example demonstrates how to make an HTTP GET request to an API and process the response.

```flexa
using flx.core.HTTP;
using flx.std.DSL.JSON;
using flx.std.structs;

include namespace flx;

fun fetch_data(url: string): any {
  try {
    var response = request(HttpConfig {
      hostname=url,
      method=GET
    });
    if (response.status == 200) {
      var data = json_parse(response.data);
      return data;
    } else {
      throw "Failed to fetch data: " + response.status;
    }
  } catch (error) {
    println("Error fetching data: " + error);
    return null;
  }
}

var data = fetch_data("https://api.example.com/data");
if (data != null) {
  println("Received data: " + json_stringify(data));
}
```

---

## Example 3: Custom Data Structure

This example shows how to create and use a custom data structure (a stack) using Flexa's structs and functions.

```flexa
namespace my_stack;

using flx.std.structs;
using flx.std.collections.list;

include namespace flx;

struct MyStack {
  var items: List;
}

fun push(stack: MyStack, item: any): void {
  add(stack.items, item);
}

fun pop(stack: MyStack) {
  if (size(stack.items) == 0) {
    throw "Stack is empty";
  }
  delete(stack.items, size(stack.items) - 1);
}

fun peek(stack: MyStack): any {
  if (size(stack.items) == 0) {
    throw "Stack is empty";
  }
  return get(stack.items, size(stack.items) - 1);
}

fun is_empty(stack: MyStack): bool {
  return size(stack.items) == 0;
}

var stack = MyStack{};
push(stack, 10);
push(stack, 20);
push(stack, 30);

println("Top item: " + peek(stack)); // Output: 30
println("Popped item: " + pop(stack)); // Output: 30
println("Is stack empty? " + is_empty(stack)); // Output: false
```

<!-- NOT IMPLEMENTED YET
---

## Example 4: Recursive Directory Traversal

This example demonstrates how to recursively traverse a directory and list all files.

```flexa
using flx.core.files;
using flx.core.console;

fun list_files(directory: string): void {
    var entries = read_dir(directory);
    foreach (var entry in entries) {
        var path = directory + "/" + entry;
        if (is_dir(path)) {
            println("Directory: " + path);
            list_files(path); // Recursive call
        } else {
            println("File: " + path);
        }
    }
}

list_files(".");
```
-->

---

## What's Next?

Now that you've seen some advanced examples of Flexa in action, it's time to explore the **complete language reference**. Head over to the [Language Reference](language-reference) section for a detailed overview of Flexa's syntax and features.

---

[← Back to Built-in Functions](built-in-functions) | [Next: FAQ and Common Issues →](faq-and-common-issues)
