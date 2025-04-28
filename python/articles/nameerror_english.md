<!--
Meta Description: # Understanding NameError in Python: Causes, Solutions, and Examples ## Synopsis The `NameError` in Python occurs when the interpreter encounters a na...
Meta Keywords: nameerror, python, defined, not, variable
-->

# Understanding NameError in Python: Causes, Solutions, and Examples

## Synopsis
The `NameError` in Python occurs when the interpreter encounters a name that it does not recognize, typically due to an undefined variable or function. This error is a common issue for both beginners and experienced programmers, as it highlights scoping problems and typos in code.

## Documentation
### Purpose
`NameError` is an exception in Python that signifies an attempt to access a variable or function name that has not been defined in the current scope. This error helps developers identify where variables have not been properly initialized or misspelled.

### Usage
When you try to use a variable that hasn’t been assigned a value or a function that hasn't been defined, Python raises a `NameError`. The basic syntax for handling exceptions, including `NameError`, is through the `try` and `except` blocks.

#### Example Syntax
```python
try:
    # Code that may raise an exception
    print(my_variable)
except NameError as e:
    # Handle the NameError
    print(f"NameError: {e}")
```

### Details
- **Scope**: Variables must be defined in the scope where they are accessed. A variable defined inside a function cannot be accessed outside of it.
- **Typographical Errors**: Simple typos can cause `NameError`. Python is case-sensitive, so `MyVariable` and `myvariable` are considered different names.
- **Imports**: If you forget to import a module or a specific function from a module, trying to use that object will raise a `NameError`.
- **Order of Execution**: If a variable is referenced before it is assigned, a `NameError` will occur.

## Examples
### Example 1: Basic NameError
```python
print(x)  # Raises NameError: name 'x' is not defined
```

### Example 2: NameError due to Typos
```python
my_variable = 10
print(my_varible)  # Raises NameError: name 'my_varible' is not defined
```

### Example 3: Scope Issue
```python
def my_function():
    y = 5

my_function()
print(y)  # Raises NameError: name 'y' is not defined
```

### Example 4: Missing Import
```python
# Uncommenting the next line will raise NameError
# from math import sqrt
print(sqrt(16))  # Raises NameError: name 'sqrt' is not defined
```

## Explanation
### Common Pitfalls
- **Undeclared Variables**: Always ensure that variables are declared and initialized before use.
- **Naming Conflicts**: Avoid using similar variable names that can lead to confusion.
- **Function Scope**: Be mindful of variable scope, especially when working with nested functions or classes.

### Additional Notes
- `NameError` can be caught and handled using the `try-except` construct to prevent program crashes.
- Utilizing tools like linters or IDEs can help catch potential `NameError` issues before runtime.

## One Line Summary
`NameError` in Python occurs when trying to access a variable or function name that has not been defined in the current scope.