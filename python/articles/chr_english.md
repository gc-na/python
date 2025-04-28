<!--
Meta Description: # Python `chr()` Function: Convert Integer to Character ## Synopsis The `chr()` function in Python is a built-in utility that converts an integer repr...
Meta Keywords: chr, character, unicode, python, integer
-->

# Python `chr()` Function: Convert Integer to Character

## Synopsis
The `chr()` function in Python is a built-in utility that converts an integer representing a Unicode code point into its corresponding character. This function is essential for text processing, string manipulation, and developing applications that require character encoding.

## Documentation
### Purpose
The `chr()` function is used to convert an integer (in the range of 0 to 1,114,111) to its corresponding Unicode character. It is particularly useful when working with character encodings and when you need to generate characters dynamically based on their Unicode values.

### Usage
The basic syntax of the `chr()` function is:
```python
chr(i)
```
Where `i` is an integer representing a Unicode code point. The function returns a string containing the character corresponding to the specified code point.

### Details
- **Parameter**: 
  - `i`: An integer (0 ≤ i ≤ 1,111,411) which represents the Unicode code point of the character.
- **Return Value**: 
  - Returns a string of one character.
- **Exceptions**: 
  - Raises a `ValueError` if the integer is out of the valid range (less than 0 or greater than 1,111,411).

## Examples
### Example 1: Basic Character Conversion
```python
# Convert integer to character
char_a = chr(97)
print(char_a)  # Output: 'a'
```

### Example 2: Special Characters
```python
# Convert integer to special character
char_special = chr(33)
print(char_special)  # Output: '!'
```

### Example 3: Unicode Characters
```python
# Convert integer to Unicode character
char_unicode = chr(9786)
print(char_unicode)  # Output: '☺'
```

### Example 4: Using a Loop
```python
# Print characters for a range of Unicode values
for i in range(65, 91):  # A-Z
    print(chr(i), end=' ')  # Output: A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
```

## Explanation
While the `chr()` function is straightforward, some common pitfalls include:
- **Out of Range Values**: Providing integers that fall outside the valid range will raise a `ValueError`. Always ensure the integer value is valid.
- **Understanding Unicode**: Unicode encompasses a vast range of characters from different languages and symbols. Familiarity with Unicode encoding can enhance the use of the `chr()` function.
- **String Type**: The output of `chr()` is of type `str`, which may behave differently in Python 2.x compared to Python 3.x. In Python 3.x, the `str` type is Unicode by default.

## One Line Summary
The `chr()` function in Python converts an integer Unicode code point into its corresponding character.