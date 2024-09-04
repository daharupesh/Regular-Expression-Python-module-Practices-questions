
# Regular Expression Module in Python (`re`)

## Overview

The `re` module in Python provides support for working with Regular Expressions (regex), a powerful tool for matching and manipulating text based on patterns. This module allows you to search for patterns within strings, replace parts of strings, and extract information, among other things.

Regular Expressions are widely used in text processing tasks such as validation, parsing, and data extraction. This `README.md` file provides a detailed guide to using the `re` module in Python.

---

## Installation

The `re` module is included with Python's standard library, so no installation is required. Simply import the module in your script:

```python
import re
```

---

## Key Functions in the `re` Module

### 1. `re.compile(pattern, flags=0)`

- **Description**: Compiles a regular expression pattern into a regular expression object, which can be used for matching using its methods.
- **Usage**:
  ```python
  regex = re.compile(r'\d+')  # Matches one or more digits
  ```

### 2. `re.match(pattern, string, flags=0)`

- **Description**: Attempts to match a pattern at the beginning of the string.
- **Returns**: A match object if successful, `None` otherwise.
- **Usage**:
  ```python
  match = re.match(r'\d+', '123abc')
  if match:
      print("Match found:", match.group())
  ```

### 3. `re.search(pattern, string, flags=0)`

- **Description**: Searches the string for the first occurrence of the pattern.
- **Returns**: A match object if the pattern is found, `None` otherwise.
- **Usage**:
  ```python
  match = re.search(r'\d+', 'abc123def')
  if match:
      print("Match found:", match.group())
  ```

### 4. `re.findall(pattern, string, flags=0)`

- **Description**: Finds all occurrences of the pattern in the string and returns them as a list.
- **Returns**: A list of strings.
- **Usage**:
  ```python
  matches = re.findall(r'\d+', 'abc123def456ghi')
  print("Matches found:", matches)
  ```

### 5. `re.finditer(pattern, string, flags=0)`

- **Description**: Returns an iterator yielding match objects for all non-overlapping matches of the pattern in the string.
- **Usage**:
  ```python
  for match in re.finditer(r'\d+', 'abc123def456ghi'):
      print("Match found:", match.group())
  ```

### 6. `re.sub(pattern, repl, string, count=0, flags=0)`

- **Description**: Replaces occurrences of the pattern in the string with the replacement string `repl`.
- **Returns**: The modified string.
- **Usage**:
  ```python
  result = re.sub(r'\d+', '#', 'abc123def456ghi')
  print("Modified string:", result)
  ```

### 7. `re.split(pattern, string, maxsplit=0, flags=0)`

- **Description**: Splits the string by the occurrences of the pattern.
- **Returns**: A list of strings.
- **Usage**:
  ```python
  result = re.split(r'\d+', 'abc123def456ghi')
  print("Split result:", result)
  ```

### 8. `re.fullmatch(pattern, string, flags=0)`

- **Description**: Checks if the entire string matches the pattern.
- **Returns**: A match object if the whole string matches, `None` otherwise.
- **Usage**:
  ```python
  match = re.fullmatch(r'\d+', '123456')
  if match:
      print("Full match found:", match.group())
  ```

### 9. `re.escape(string)`

- **Description**: Escapes all non-alphanumeric characters in the string, making it suitable for use in a regular expression pattern.
- **Usage**:
  ```python
  escaped_string = re.escape('Hello, World!')
  print("Escaped string:", escaped_string)
  ```

---

## Match Object Methods

When you successfully find a match using `re.match()`, `re.search()`, `re.fullmatch()`, or `re.finditer()`, a match object is returned. The match object provides several methods and attributes:

- **`group()`**: Returns the entire match or specific groups if the pattern contains capturing groups.
- **`start()`**: Returns the start position of the match.
- **`end()`**: Returns the end position of the match.
- **`span()`**: Returns a tuple containing the start and end positions of the match.

### Example

```python
match = re.search(r'(\d+)', 'abc123def')
if match:
    print("Matched group:", match.group(1))
    print("Start position:", match.start(1))
    print("End position:", match.end(1))
    print("Span:", match.span(1))
```

---

## Common Regular Expression Patterns

Here are some commonly used regular expression patterns:

- **`\d`**: Matches any digit; equivalent to `[0-9]`.
- **`\w`**: Matches any alphanumeric character; equivalent to `[a-zA-Z0-9_]`.
- **`\s`**: Matches any whitespace character (spaces, tabs, line breaks).
- **`.`**: Matches any character except a newline.
- **`^`**: Matches the start of the string.
- **`$`**: Matches the end of the string.
- **`*`**: Matches 0 or more repetitions of the preceding pattern.
- **`+`**: Matches 1 or more repetitions of the preceding pattern.
- **`?`**: Matches 0 or 1 repetition of the preceding pattern.
- **`{m,n}`**: Matches from `m` to `n` repetitions of the preceding pattern.

---

## Example Usage

```python
import re

# Example: Extract all email addresses from a text
text = "Contact us at support@example.com and sales@example.co.uk"
emails = re.findall(r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b', text)
print("Email addresses found:", emails)
```

---

## Conclusion

The `re` module is an essential tool for anyone working with text processing in Python. By mastering regular expressions, you can perform complex pattern matching and text manipulation with ease. This README provides a foundation for understanding and using the `re` module effectively in your projects.
