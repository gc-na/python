<!--
Meta Description: # Understanding LookupError in Python: A Comprehensive Guide ## Synopsis `LookupError` is a built-in exception in Python that is raised when a key or ...
Meta Keywords: lookuperror, key, python, when, not
-->

# Understanding LookupError in Python: A Comprehensive Guide

## Synopsis
`LookupError` is a built-in exception in Python that is raised when a key or index used to access a collection, such as a list or dictionary, is not found. This error is essential for handling cases where data retrieval fails due to non-existent keys or indices.

## Documentation

### Purpose
`LookupError` serves as a base class for all exceptions that occur when a look-up operation fails. It is part of the hierarchy of built-in exceptions in Python and is subclassed by more specific exceptions such as `IndexError` and `KeyError`.

### Usage
In Python programming, `LookupError` can be caught using a try-except block, allowing developers to handle the error gracefully rather than letting the program crash. This is particularly useful when dealing with data structures where user input may lead to invalid lookups.

### Details
- **Type**: Built-in Exception
- **Hierarchy**: Inherits from `Exception`
- **Subclasses**:
  - `KeyError`: Raised when a dictionary key is not found.
  - `IndexError`: Raised when a sequence index is out of range.

To raise a `LookupError`, you can use the `raise` statement, but it is more common to encounter it through its subclasses.

## Examples

### Example 1: Using KeyError
```python
my_dict = {'name': 'Alice', 'age': 30}

try:
    print(my_dict['gender'])
except KeyError as e:
    print(f"KeyError: {e} - Key does not exist.")
```
*Output:*
```
KeyError: 'gender' - Key does not exist.
```

### Example 2: Using IndexError
```python
my_list = [1, 2, 3]

try:
    print(my_list[5])
except IndexError as e:
    print(f"IndexError: {e} - Index is out of range.")
```
*Output:*
```
IndexError: list index out of range - Index is out of range.
```

### Example 3: Catching LookupError
```python
def get_value(data, key):
    try:
        return data[key]
    except LookupError as e:
        return f"LookupError: {e} - Key not found."

result = get_value({'name': 'Bob'}, 'age')
print(result) 
```
*Output:*
```
LookupError: 'age' - Key not found.
```

## Explanation
Common pitfalls when dealing with `LookupError` include:
- Ignoring specific exceptions: It can be easy to overlook the subclass exceptions like `KeyError` and `IndexError`. Catching `LookupError` may not always provide the most specific feedback about the error.
- Failing to validate data: Always ensure that keys or indices are checked before attempting to access them to prevent unnecessary exceptions.
- Misunderstanding the hierarchy: Knowing that `LookupError` is a parent class can help in designing better exception handling strategies.

When designing functions that may raise `LookupError`, consider documenting your code to help other developers understand potential exceptions they may encounter.

## One Line Summary
`LookupError` is a built-in exception in Python that indicates a failure in retrieving an item from a collection due to a non-existent key or index.