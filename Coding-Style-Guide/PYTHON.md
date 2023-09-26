# Python Coding Style Guide

This document outlines the recommended coding style guidelines for Python developers. Following a consistent coding style improves code readability, maintainability, and collaboration among team members.

## Indentation and Line Length

- Use 4 spaces for indentation. Avoid using tabs.
- Limit each line to a maximum of 79 characters. For long lines, you can break them into multiple lines using parentheses or backslashes for better readability.

```python
# Example of line continuation
result = (first_variable + second_variable +
          third_variable - fourth_variable)

# Example of breaking long lines
my_long_list = [
    'item1', 'item2', 'item3', 'item4', 'item5', 'item6',
    'item7', 'item8', 'item9', 'item10'
]

```

## Naming Conventions

- Use descriptive names for variables, functions, classes, and modules.
- Use lowercase letters for variable and function names. Separate words with underscores (snake_case).
- Use CamelCase for class names.
- Use all capital letters for constants, with words separated by underscores.

```python
# Variable and function names
my_variable = 42
calculate_sum = lambda x, y: x + y

# Class name
class MyClass:
    pass

# Constant name
PI = 3.14159
```

## Imports

- Import modules individually rather than using wildcard imports.
- Order imports in the following order: standard library modules, third-party modules, local project modules.
- Separate import groups with a blank line.
- Avoid using relative imports (from . import module).

```python
# Correct import order
import os
import sys

import requests
import numpy as np

from my_package import module1, module2
```

## Function and Method Definitions

- Use lowercase letters for function and method names. Separate words with underscores (snake_case).
- Use docstrings to provide a brief description of the function or method's purpose, input parameters, and return values.
- Follow the PEP 484 guidelines for type hints to improve code readability and maintainability.

```python
def calculate_sum(a: int, b: int) -> int:
    """Calculate the sum of two integers."""
    return a + b
```

## Comments

- Use comments to explain complex logic, provide context, or clarify the code's intent. Comments should be concise and to the point.
- Avoid unnecessary or redundant comments that merely restate the code.
- Write docstrings for functions, classes, and modules to provide detailed explanations of their purpose, parameters, and return values.

```python
# This comment explains a complex calculation
result = (a + b) / (c - d)  # Dividing the sum by the difference

def calculate_sum(a: int, b: int) -> int:
    """Calculate the sum of two integers.

    Args:
        a: The first integer.
        b: The second integer.

    Returns:
        The sum of the two integers.
    """
    return a + b
```

## Miscellaneous

- Use spaces around operators (=, +, -, \*, /, etc.) for improved readability.
- Avoid using unnecessary parentheses unless they improve code clarity.
- Follow the Zen of Python principles (PEP 20) for writing clean, readable, and Pythonic code.

```python
# Examples of spacing and parentheses
x = (a + b) / c  # Good
y = a*b + c/d  # Good
z = a*(b + c)  # Good
z = a * (b + c)  # Better (more readable)
```

## Error Handling

- Always include appropriate error handling in your code. Use try-except blocks to catch and handle exceptions when necessary.
- Handle specific exceptions whenever possible instead of using a bare except clause.
- Provide informative error messages to help with troubleshooting and debugging.

```python
try:
    # Code that may raise an exception
    ...
except ValueError as e:
    # Handling ValueError
    ...
except FileNotFoundError as e:
    # Handling FileNotFoundError
    ...
except Exception as e:
    # Handling other exceptions
    ...
```

## String Formatting

- Prefer f-strings (formatted string literals) for string formatting.
- Use meaningful variable names within f-strings to improve readability.

```python
name = 'Alice'
age = 30

# Preferred string formatting using f-strings
greeting = f"Hello, {name}! You are {age} years old."

print(greeting)  # Output: Hello, Alice! You are 30 years old.
```

## List Comprehensions and Generator Expressions

- Use list comprehensions and generator expressions for concise and readable code when constructing lists or iterating over sequences.
- Avoid using them for complex logic that sacrifices readability.

```python
# List comprehension example
squares = [x**2 for x in range(1, 11)]

# Generator expression example
even_numbers = (x for x in range(1, 11) if x % 2 == 0)
```

## Avoid Using Single Underscores for Weak "Internal Use" Indication

- By convention, a single leading underscore is often used to indicate weak "internal use" within a module or class. However, in practice, it doesn't prevent the use of those variables or methods from outside the module or class.
- Consider using a double underscore (\_\_) prefix for "internal use" variables or methods to provide stronger indication and avoid accidental usage from outside.

```python
class MyClass:
    def __init__(self):
        self.__internal_variable = 42

    def __internal_method(self):
        pass
```

By adhering to these coding style guidelines, you will create Python code that is consistent, readable, and easier to maintain, enabling effective collaboration and understanding among developers.

## References

- [PEP 8 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)
- [PEP 20 -- The Zen of Python](https://www.python.org/dev/peps/pep-0020/)
- [PEP 257 -- Docstring Conventions](https://www.python.org/dev/peps/pep-0257/)
- [PEP 484 -- Type Hints](https://www.python.org/dev/peps/pep-0484/)
