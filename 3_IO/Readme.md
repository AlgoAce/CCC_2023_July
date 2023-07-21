

# Building Functions

```Python
>>> abs(-1)
1
>>> int(2.3)
2
>>> float(1)
1.0
>>> round(0.5)
1
>>> max(2, 3)
3
>>> type(1.23)
float
>>> isinstance(2, int)
True
```


# Input and Output

## Input

### User Input to a Python Program

```python
user_input = input()
```

```python
prompt = "Enter the number you want to use: "
user_input = input(prompt)
```


```python
city = input("Enter hometown: ")
```


**Example**: Input sum

Write the Python function <strong>add</strong> that reads a natural number <strong>a</strong> and a natural number <strong>b</strong> from the user via the keyboard, and prints out it's sum.

```python
def add():
    a = input("Enter the first number")
    b = input("Enter the second number")

    a = int(a)
    b = int(b)
    return a + b
```

## Print

**Basic Usage of print**

The print function in Python is a built-in function that allows you to display output to the console. It is a handy tool for displaying values, debugging, or providing information to users.

The simplest way to use the print function is to pass a single argument, which can be a string, number, or any other data type. The print function will convert the argument to a string (if it's not already a string) and display it on the console.

```python
print("Hello, World!")
print(42)
print(3.14159)
```

**Printing Multiple Arguments**

You can also pass multiple arguments to the print function, separated by commas. The print function will convert each argument to a string and concatenate them, separated by a space.

```python
name = "John"
age = 30
print("My name is", name, "and I am", age, "years old.")
```

**Customizing the Separator**

```python
print("Python", "is", "awesome", sep="-")
```

**Printing with Newline Characters**

```python
print("This is line 1.\nThis is line 2.")
```

**Customizing the End Character**

```python
print("This is a single line", end=".")
```

## Print vs Return

**Key Differences**
- Purpose: print is used for displaying output to the console, while return is used for passing a value back to the caller.
- Functionality: print has no impact on the program's flow or data storage, while return terminates the function and provides a value for further use.
- Output: When using print, the output is visible on the console. In contrast, a return statement does not produce visible output, but instead provides a value that can be assigned to a variable or used in other computations.


**Example:** Print Square
```python
def print_square(x):
    print(x * x)

def return_square(x):
    return x * x

# Using the print function
print_square(4)  # Output: 16

# Using the return statement
result = return_square(4)
print(result)  # Output: 16

# Using the return statement
result = return_square(return_square)
print(result)  # Output: 256

# Using the print function
print_square(print_square(4))  # BUG

```

**Exercise**: Special Day II

***Problem Description***

February 18 is a special date for the CCC this year.

Write a program that asks the user for a numerical month and numerical day of the month and then
determines whether that date occurs before, after, or on February 18.

If the date occurs before February 18, output the word Before. If the date occurs after February
18, output the word After. If the date is February 18, output the word Special.

***Input Specification***

The input consists of two integers each on a separate line. These integers represent a date in 2015.
The first line will contain the month, which will be an integer in the range from 1 (indicating
January) to 12 (indicating December).

The second line will contain the day of the month, which will be an integer in the range from 1 to 31. You can assume that the day of the month will be valid for the given month.

***Output Specification***

Exactly one of Before, After or Special will be printed on one line
**Sample Input 1**

```
Enter the month: 1
Enter the date: 7
```

**Output for Sample Input 1**

```
Before
```

**Sample Input 2**

```
Enter the month: 8
Enter the date: 31
```

**Output for Sample Input 2**

```
After
```

**Sample Input 3**

```
Enter the month: 2
Enter the date: 18
```

**Output for Sample Input 3**

```
Special
```

```python
def Special_Day():
    pass
```
<br/>

# Import Module

Python has a vast ecosystem of libraries and modules that provide additional functionality beyond the built-in features. To access and use these libraries and modules, you need to import them into your script. 

https://docs.python.org/3/library/math.html

**Basic Import**
```Python
import math

# Now you can use the functions and constants from the math module
result = math.sqrt(25)
print(result)  # Output: 5.0
```

**Importing Specific Functions or Classes**

Instead of importing the entire module, you can import specific functions or classes using the from ... import ... syntax. This allows you to use the imported functions or classes directly, without the need for dot notation.

```Python
from math import sqrt, pow

# You can use the imported functions directly
result1 = sqrt(25)
result2 = pow(2, 3)
print(result1, result2)  # Output: 5.0 8.0
```


**Importing with Aliases**

In some cases, you may want to use an alias (shorter or alternative name) for an imported module or function to improve readability or avoid naming conflicts. To do this, use the as keyword.


```Python
import math as m

# You can now use the module's functions with the alias
result = m.sqrt(25)
print(result)  # Output: 5.0
```

