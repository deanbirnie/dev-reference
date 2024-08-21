
# Python Docstring Cheatsheet

This cheatsheet provides a quick reference for writing Python docstrings using the reStructuredText (reST) style. It includes examples for various types of methods and provides links to official documentation for further reading.

## General Structure of a reST Docstring

```python
def function_name(params):
    """
    Brief description of what the function does.

    :param param_name: Description of the parameter.
    :type param_name: The type of the parameter.

    :return: Description of the return value.
    :rtype: The type of the return value.

    :raises ExceptionType: Description of the condition under which the exception is raised.

    """
    pass
```

## Sections

### 1. Summary Line

The summary line should be a brief description of the function's purpose. It should start with a capital letter and end with a period.

### 2. Parameters (`:param` and `:type`)

Use the `:param` directive to describe each parameter and the `:type` directive to specify the type of the parameter.

```python
def add(a: int, b: int) -> int:
    """
    Adds two integers together.

    :param a: The first integer to add.
    :type a: int

    :param b: The second integer to add.
    :type b: int

    :return: The sum of `a` and `b`.
    :rtype: int

    """
    return a + b
```

### 3. Return Values (`:return` and `:rtype`)

Document the return value using the `:return` directive and specify its type with the `:rtype` directive.

```python
def get_greeting(name: str) -> str:
    """
    Generates a greeting message.

    :param name: The name of the person to greet.
    :type name: str

    :return: A greeting string.
    :rtype: str

    """
    return f"Hello, {name}!"
```

### 4. Exceptions (`:raises`)

Document any exceptions that the function might raise using the `:raises` directive.

```python
def divide(a: int, b: int) -> float:
    """
    Divides `a` by `b`.

    :param a: The dividend.
    :type a: int

    :param b: The divisor.
    :type b: int

    :return: The result of the division.
    :rtype: float

    :raises ZeroDivisionError: If `b` is zero.

    """
    if b == 0:
        raise ZeroDivisionError("Division by zero is not allowed.")
    return a / b
```

### 5. Multiple Parameters and Returns

For functions with multiple parameters or return values, list each one on a separate line.

```python
def process_data(data: list, method: str = "average") -> tuple:
    """
    Processes data using the specified method.

    :param data: A list of numerical values.
    :type data: list

    :param method: The method to process data. Options are "average", "sum". Defaults to "average".
    :type method: str

    :return: A tuple containing the processed result and the method used.
    :rtype: tuple

    :raises ValueError: If an unsupported method is provided.

    """
    if method == "average":
        return sum(data) / len(data), method
    elif method == "sum":
        return sum(data), method
    else:
        raise ValueError("Unsupported method provided.")
```

### 6. Classes and Methods

For classes, provide a summary of the class's purpose. For methods, follow the same structure as functions.

```python
class Calculator:
    """
    A simple calculator class that can perform basic arithmetic operations.
    """

    def add(self, a: int, b: int) -> int:
        """
        Adds two integers.

        :param a: The first integer to add.
        :type a: int

        :param b: The second integer to add.
        :type b: int

        :return: The sum of `a` and `b`.
        :rtype: int

        """
        return a + b

    def subtract(self, a: int, b: int) -> int:
        """
        Subtracts `b` from `a`.

        :param a: The number from which to subtract.
        :type a: int

        :param b: The number to subtract.
        :type b: int

        :return: The result of the subtraction.
        :rtype: int

        """
        return a - b
```

## Special Cases

### 1. No Return Value (`None`)

If a function does not return a value, you can indicate this by specifying `None` as the return type.

```python
def print_message(message: str) -> None:
    """
    Prints a message to the console.

    :param message: The message to print.
    :type message: str

    :return: None
    :rtype: None

    """
    print(message)
```

### 2. Optional Parameters

For optional parameters, you can specify the type using `Optional` from the `typing` module.

```python
from typing import Optional

def greet(name: Optional[str] = None) -> str:
    """
    Greets the user by name, or provides a generic greeting if no name is given.

    :param name: The name of the person to greet, or None.
    :type name: Optional[str]

    :return: A greeting message.
    :rtype: str

    """
    if name:
        return f"Hello, {name}!"
    else:
        return "Hello, there!"
```

## Additional Resources

- [PEP 257 - Python Docstring Conventions](https://www.python.org/dev/peps/pep-0257/ "PEP 257 - Python Docstring Conventions" target="_blank")
- [reStructuredText (reST) for Docstrings](https://docutils.sourceforge.io/rst.html "reStructuredText (reST) for Docstrings"  target="_blank")
- [Google Style Guide for Python Docstrings](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings "Google Style Guide for Python Docstrings"  target="_blank")
- [Sphinx Documentation Generator](https://www.sphinx-doc.org/en/master/ "Sphinx Documentation Generator"  target="_blank")

This cheatsheet should help you write clear, concise, and consistent docstrings using the reST style. Keep it handy as a reference for future projects!
