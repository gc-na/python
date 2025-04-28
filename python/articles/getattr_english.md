<!--
Meta Description: # Understanding `getattr` in Python: Accessing Object Attributes Dynamically ## Synopsis `getattr` is a built-in Python function that retrieves the va...
Meta Keywords: attribute, getattr, name, not, default
-->

# Understanding `getattr` in Python: Accessing Object Attributes Dynamically

## Synopsis
`getattr` is a built-in Python function that retrieves the value of an attribute from an object dynamically using a string as the attribute name. It is especially useful for accessing attributes when their names are not known until runtime.

## Documentation

### Purpose
The `getattr` function allows developers to access an attribute of an object using a string. This is particularly helpful in cases where attributes may vary based on user input, configuration files, or other dynamic conditions.

### Usage
The syntax for `getattr` is as follows:

```python
getattr(object, name[, default])
```

- **object**: The object whose attribute you want to access.
- **name**: A string representing the name of the attribute you wish to retrieve.
- **default** (optional): A value to return if the specified attribute does not exist. If not provided and the attribute is not found, an `AttributeError` will be raised.

### Details
- If the attribute exists in the object, `getattr` will return its value.
- If the attribute does not exist and the default value is specified, `getattr` will return the default value instead of raising an error.
- If the attribute does not exist and no default value is provided, an `AttributeError` will be raised.

## Examples

### Basic Example
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person("Alice", 30)

# Accessing attributes using getattr
name = getattr(person, 'name')  # Returns "Alice"
age = getattr(person, 'age')     # Returns 30

print(name)  # Output: Alice
print(age)   # Output: 30
```

### Example with Default Value
```python
# Attempting to access a non-existing attribute with default
hobby = getattr(person, 'hobby', 'Not specified')  # Returns "Not specified"

print(hobby)  # Output: Not specified
```

### Example Raising AttributeError
```python
# Attempting to access a non-existing attribute without default
try:
    country = getattr(person, 'country')  # Raises AttributeError
except AttributeError as e:
    print(e)  # Output: 'Person' object has no attribute 'country'
```

## Explanation
While `getattr` is a powerful tool, there are some common pitfalls to be aware of:

- **AttributeError**: If you try to access an attribute that does not exist and do not provide a default value, `getattr` will raise an `AttributeError`. It's good practice to use the default parameter when there's a chance the attribute might not exist.
  
- **Dynamic Attribute Access**: Using `getattr` can be less readable compared to direct attribute access (e.g., `person.name`). Overusing dynamic access might lead to code that is harder to understand and maintain.

- **Security Implications**: If the attribute name is derived from user input, there could be security implications, such as accessing sensitive attributes unintentionally. Always validate and sanitize user input when using `getattr`.

## One Line Summary
`getattr` is a Python built-in function that retrieves an object's attribute value dynamically using a string, with an optional default value to prevent errors for missing attributes.