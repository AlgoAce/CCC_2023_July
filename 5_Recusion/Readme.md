- [Recursion](#recursion)
  - [Structural Recursion](#structural-recursion)
  - [Accumulative Recursion](#accumulative-recursion)
  - [Generative Recursion](#generative-recursion)
# Recursion

## Structural Recursion
```Python
# The following function calculate n!
def factorial(n):
    # Base case
    if n == 0:              
        return 1
    else:
        return n * factorial(n-1)
```
Trace factorial

```Python
factorial(6)
=> 6 * factorial(5)
=> 6 * (5 * factorial(4))
=> 6 * (5 * (4 * factorial(3)))
=> 6 * (5 * (4 * (3 * factorial(2))))
=> 6 * (5 * (4 * (3 * (2 * factorial(1))))) 
=> 6 * (5 * (4 * (3 * (2 * 1))))
=> 720
```
In our recursive call, our recursive data is one step closer to the base case

**Example**: Condiser the following function
```Python
# The following function find the maximum numebr in a list
def findMax(lst):
    if (len(lst) == 1):
        return lst[0]
    elif (lst[0] > findMax(lst[1:])):
        return lst[0]
    else:
        return findMax(lst[1:])
```
Try to trace 
```Python
findMax([1, 2, 3, 4])
=> 1 > findMax([2, 3, 4])
=> 2 > findMax([3, 4])
=> elif 3 > findMax([4]) => False 
=> findMax([4])
=> 2 > 4
=> findMax([3, 4])
```

## Accumulative Recursion
Consider the another way to implement findMax.
```Python
# Helper function
def remember_max(m, lst):       
    # Base Case
    if len(lst)==0:             
        return m
    elif m > lst[0]:
        return remember_max(m, lst[1:])
    else:
        return remember_max(lst[0], lst[1:])

def findMax2(lst):
    return remember_max(lst[0], lst[1:])
```
Try to trace the following, why is findMax2 faster than findMax?
```Python
findMax2([1, 2, 3, 4])


```

Why use Accumulative Recursion?
- Might make better use of space
- Might help code run faster (... or not)
- But may be harder to trace or test

The Accumulative Recursion Following the below pattern
```Python
def acc_helper(acc, remaining, ...):
    if at stopping case
        return (answer using acc)
    else:
        return acc_helper(updated acc, update remaining. ...)

def fn(...):
    acc_helper(initial acc, initial remaining, ...)
```

**Exercise:** Fibonacci numbers
The nth Fibonacci number is the sum of the two previous Fibonacci numbers:
$$
f_n = f_{n-1} + f_{n - 2}, \text{ where } f_0 = 0, f_1 = 1.
$$
Write a function that calculate the Fibonacci numbers:

```Python
# fib(5) => 5
# fib(10) => 55
# fib(35) => 9,227,465
def fib(n):

```
**Exercise:** Reversing a List
```Python
# reverse([0]) => 0
# reverse([1, 3, 5, 2]) => [2, 5, 3, 1]
def reverse(n):

```

**Exercise:** Check is palindrome.
A palindrome is a string that reads the same forwards and backwards, for example, "abcba" or"12 33 21".

Write a recursive Python function is_palindrome that consumes a string (s), and produces True if s is a palindrome, and False if not. Note that any string of length less than 2 is a palindrome.

```Python
# palindrome("a") => True
# reverse("12321") => True
def palindrome(s):

```


## Generative Recursion
Consider new ways (other than the definition of the data) to break into subproblems.

**Example**: The greatest common divisor (gcd) of two natural numbers is the largest natural number that divides evenly into both.
```Python
gcd(25, 10) => 5
gcd(22, 10) => 2
gcd(39, 26) => 13
```

```Python
# Euclid’s Algorithm for gcd
def gcd(m,n):
    if m==0: 
        return n
    elif n==0: 
        return m
    else: 
        return gcd(n, m % n)
```
Tracing gcd:
```
gcd(25, 10)
=> gcd(10, 25 % 10)
=> gcd(10, 5)
=> gcd(5, 10 % 5) 
=> gcd(5, 0)
=> 5
```

**Exercise**: Reverse a number. 

Write a function Reverse that consumes a natural number and produces a new number with the digits in reverse order.

- Consider the number n = 5678, Divide the number into:
    – Last digit: 8
    – Everything else: 567
- Next, reverse 567
    – Take last digit (7) and "add to" 8 => 87
    – What's left? 56
- Repeat the process until all digits processed

```Python
# reverse(0) => 0
# reverse(7654) => 4567
# reverse(10011) => 11001
def Reverse(n):
    pass
```

