# C++ Coding Style Guide

This document outlines the recommended coding style guidelines for C++ developers. Following a consistent coding style improves code readability, maintainability, and collaboration among team members.

## Indentation and Line Length

- Use 4 spaces for indentation. Avoid using tabs.
- Limit each line to a maximum of 79 characters. For long lines, you can break them into multiple lines using parentheses or backslashes for better readability.

```cpp
// Example of line continuation
int result = (first_variable + second_variable +
              third_variable - fourth_variable);

// Example of breaking long lines
std::vector<int> my_long_vector = {
    1, 2, 3, 4, 5, 6,
    7, 8, 9, 10
};
```

## Naming Conventions

- Use descriptive names for variables, functions, classes, and namespaces.
- Use lowercase letters for variable and function names. Separate words with underscores (snake_case).
- Use CamelCase for class names.
- Avoid using names that are too similar and may cause confusion.

```cpp
// Variable and function names
int my_variable = 42;
void calculate_sum(int x, int y) { /* ... */ }

// Class name
class MyClass { /* ... */ };

// Namespace name
namespace my_namespace { /* ... */ }
```

## Header Files and Include Guards

- Use include guards (header guards) to prevent multiple inclusions of the same header file.
- Use a consistent naming convention for include guards: FILENAME_H or FILENAME_HPP, where FILENAME represents the name of the header file in uppercase letters.
- Organize include directives in the following order: standard library headers, third-party library headers, local project headers.

```cpp
#ifndef MY_HEADER_H
#define MY_HEADER_H

// Standard library headers
#include <iostream>
#include <vector>

// Third-party library headers
#include <library/header.h>

// Local project headers
#include "my_module.h"

#endif // MY_HEADER_H
```

## Function and Method Definitions

- Use lowercase letters for function and method names. Separate words with underscores (snake_case).
- Use consistent and descriptive names for function parameters.
- Use meaningful return type names and provide comments or docstrings to describe the purpose and behavior of the function or method.

```cpp
// Function example
int calculate_sum(int a, int b) {
    // Calculate the sum of two integers
    return a + b;
}

// Method example
class MyClass {
public:
    void do_something(int value) {
        // Perform some action with the given value
    }
};
```

## Comments

- Use comments to explain complex logic, provide context, or clarify the code's intent. Comments should be concise and to the point.
- Write comments in English to facilitate collaboration among international teams.
- Write comments for non-obvious or critical sections of code to improve readability and understanding.

```cpp
// This comment explains the purpose of the following code block
int result = (a + b) / (c - d);  // Dividing the sum by the difference

// This function calculates the sum of two integers
// Parameters:
// - a: The first integer.
// - b: The second integer.
// Returns:
// The sum of the two integers.
int calculate_sum(int a, int b) {
    return a + b;
}
```

## Miscellaneous

- Use meaningful and descriptive variable names to improve code readability.
- Use appropriate spacing around operators (=, +, -, \*, /, etc.) for improved readability.
- Follow the principles of the C++ Core [Guidelines](https://github.com/isocpp/CppCoreGuidelines) for writing clean, readable, and idiomatic C++ code.

## Error Handling

- Always include appropriate error handling in your code. Use try-catch blocks to catch and handle exceptions when necessary.
- Handle specific exceptions whenever possible instead of using a catch-all (catch (...)).
- Provide informative error messages to help with troubleshooting and debugging.

```cpp
try {
    // Code that may throw an exception
    // ...
} catch (const std::exception& e) {
    // Handling specific exception types
    std::cerr << "Error: " << e.what() << std::endl;
} catch (...) {
    // Handling unknown exceptions
    std::cerr << "Unknown error occurred." << std::endl;
    throw; // Re-throw the exception if necessary
}
```

## Const-Correctness

- Use const whenever possible to indicate that a variable, parameter, or member function does not modify the state of an object.
- Use const references for parameters that are not modified within a function to avoid unnecessary copies.

```cpp
// Example of const-correctness
class MyClass {
public:
    void print_data() const {
        // Print data without modifying the object
        std::cout << data_ << std::endl;
    }

private:
    int data_;
};

void process_data(const std::vector<int>& values) {
    // Process values without modifying the vector
    // ...
}
```

## Memory Management

- Prefer smart pointers (std::unique_ptr, std::shared_ptr) and RAII (Resource Acquisition Is Initialization) principles for automatic memory management.
- Avoid using raw pointers whenever possible to minimize manual memory management and the risk of memory leaks.

```cpp
// Example of smart pointers and RAII
void do_something() {
    std::unique_ptr<MyClass> ptr = std::make_unique<MyClass>(); // Automatic memory management
    // ...
}

class Resource {
public:
    Resource() {
        // Acquire resources during construction
    }

    ~Resource() {
        // Release resources during destruction
    }
};
```

### Naming Conventions for Constants

- Use ALL_CAPS_WITH_UNDERSCORES for naming constants.
- Prefix constants with a suitable namespace or class name to avoid naming conflicts.

```cpp
// Naming convention for constants
const int MAX_VALUE = 100;
const double PI = 3.14159;

namespace MathConstants {
    const double E = 2.71828;
}
```

By adhering to these coding style guidelines, you will create C++ code that is consistent, readable, and easier to maintain, enabling effective collaboration and understanding among developers.

## References

- [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
- [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines)
