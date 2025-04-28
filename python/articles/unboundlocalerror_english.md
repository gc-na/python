<!--
Meta Description: # UnboundLocalError in Python: Understanding, Causes, and Solutions ## Synopsis UnboundLocalError is a specific type of error in Python that occurs wh...
Meta Keywords: variable, unboundlocalerror, local, python, before
-->

# UnboundLocalError in Python: Understanding, Causes, and Solutions

## Synopsis
UnboundLocalError is a specific type of error in Python that occurs when a local variable is referenced before it has been assigned a value. This error is crucial for developers to understand as it often indicates logical mistakes in the code.

## Documentation
### Purpose
UnboundLocalError is raised when a local variable is referenced before it has been assigned. This typically happens within a function or a nested scope where the variable is intended to be local but has not been initialized. 

### Usage
UnboundLocalError is part of Python's built-in exceptions and is a subclass of NameError. It is automatically triggered by the Python interpreter during code execution when it detects an attempt to use a local variable that hasn’t been assigned a value.

### Details
- **Scope**: Local variables are defined within a function and are not accessible outside of that function. If a local variable is referenced without being assigned, Python raises an UnboundLocalError.
- **Global Variables**: If there is a global variable with the same name as a local variable, using the variable inside a function without assigning to it first will lead to this error.

## Examples
### Example 1: Basic UnboundLocalError
```python
def my_function():
    print(x)  # Attempting to print a variable before assignment
    x = 10

my_function()
```
**Output:**
```
UnboundLocalError: local variable 'x' referenced before assignment
```

### Example 2: Local and Global Variable Conflict
```python
x = 5

def my_function():
    print(x)  # This will raise UnboundLocalError
    x = 10    # Local variable assignment

my_function()
```
**Output:**
```
UnboundLocalError: local variable 'x' referenced before assignment
```

### Example 3: Correcting UnboundLocalError
```python
x = 5

def my_function():
    global x  # Declare x as global to avoid UnboundLocalError
    print(x)  # This will now correctly reference the global variable
    x = 10

my_function()
```
**Output:**
```
5
```

## Explanation
UnboundLocalError can be confusing for beginners, especially when dealing with variable scopes. Here are some common pitfalls and additional notes:

- **Shadowing Global Variables**: If a local variable is intended to shadow a global one, it must be assigned before it can be referenced. Otherwise, the interpreter will assume the variable is local and raise an UnboundLocalError.
- **Initialization**: Always initialize variables before usage within a function, especially in complex functions with multiple scopes.
- **Debugging**: When encountering this error, check the variable’s assignment and ensure that all paths in the code lead to initialization before any reference.

## One Line Summary
UnboundLocalError in Python occurs when a local variable is referenced before it has been assigned a value, highlighting issues with variable scope and initialization.