- [While Loop](#while-loop)
- [For Loop](#for-loop)
- [Differnece between for and While](#differnece-between-for-and-while)
- [Continue](#continue)
- [Break](#break)


In Python, loops are used to repeat a block of code multiple times. There are two main types of loops in Python: for loops and while loops.

# While Loop
In Python, repetition can be recursive
```Python
def count_down(x):
    if x == 0:
        return 0
    else:
        return x + count_down(x-1)
```

While loops are used when you don't know the number of times you want to repeat a block of code, but you have a condition that you want to test at the beginning of each iteration of the loop. Here's the basic syntax for a while loop in Python:

```Python
while condition:
    # code to be executed
```
In this syntax, condition is an expression that is tested at the beginning of each iteration of the loop. If condition is true, the code within the loop is executed. This process continues until condition is false.

For example, let's say you want to keep prompting the user to enter a number until they enter a number between 1 and 10. Here's how you could do it using a while loop:

```Python
num = 0
while not (1 <= num <= 10):
    num = int(input("Enter a number between 1 and 10: "))

```

In this example, the loop continues to prompt the user to enter a number until the condition not (1 <= num <= 10) is false (i.e., the user enters a number between 1 and 10).


**Example**: Checking Primality
```Python
def is_prime (n):
    test_factor = 2
    while test_factor < n:
        if n % test_factor == 0:
            return False
    else:
        test_factor = test_factor + 1
    return True
```


**Example**: Infinite Loop
```Python
while True:
    print( 'runs forever' )
```

Why we use loops instead of recursion?
- Iteration is like accumulative recursion
- Python won’t let us recurse thousands of times
- Iteration is more memory efficient
  - for each recursive call, we need memory for parameters
  - or an iterative call, we may just need to update an existing variable
- Iteration will generally run faster

**Exercise**: factorial
```Python
# fib(5) => 5
# fib(10) => 55
# fib(35) => 9,227,465
def fib(n):
    pass
```


# For Loop

For loops are used when you know the number of times you want to repeat a block of code. Here's the basic syntax for a for loop in Python

``` Python
for variable in iterable:
    # code to be executed
```

In this syntax, variable is a variable that takes on the value of each item in iterable (which could be a list, tuple, string, etc.) during each iteration of the loop. The code within the loop is executed once for each item in iterable.

For example, let's say you want to print the numbers 1 through 5 using a for loop. Here's how you could do it:

```python
for i in range(1, 6):
    print(i)
```

And here is another two example of using for.

```Python
for food in ['avocado', 'banana', 'cabbage']: 
    print(food.upper())

for base in 'ACGGGTCG':
    print(base)
```

**Exercise**: Read following code and answer the questions:
```Python
def foo(n):
  for i in range(n): # [0, 1, 2]
    if i <= 3:
      print("A")
    if i <= 2:
      print("B")
    if i <= 1:
      print("C")
```
What is the the output of running foo(3)?

**Exercise**: Multiply By
```Python
# multiply_by([1, 2], 5) => [5, 10]
def multiply_by(lst, factor):
    pass
```


# Differnece between for and While
While:
- Loop counter should be initialized outside loop
- Includes continuation test before body
- Should update loop variables in body of loop
- Body contains steps to repeat

For:
- Loop counter initialized automatically
- Continues while more elements in collection, or more values in iterator
- Loop variable updated automatically – do not update in loop
- Body contains steps to repeat
# Continue

Continue is used to skip the current iteration and continue with the next one. This means that if the continue statement is encountered in the loop, the loop will directly jump to the next iteration, skipping any code in between.

**Example**

```python
for i in range(10):
    if i == 5:
        continue
    print(i, end = ' ')

# 0 1 2 3 4 6 7 8 9 
```


# Break

The break statement in Python is used to exit a loop prematurely, before the loop has finished iterating over all of its items or before the condition in a while loop becomes false. Here's an example of how you could use the break statement in a for loop:

```Python
ans = []
for i in range(0, 10):
    ans.append(i)
    if i == 8:
        break

print(ans)
# 0, 1, 2, 3, 4, 5, 6, 7, 8
```

```Python
i = 1
while i <= 10:
    if i == 5:
        break
    print(i, end = ', ')
    i += 1

print(ans)
# 1, 2, 3, 4
```

**Exercise**:

Given a list of list of numbers, produce sum of all numbers.
```Python
sum_all ([ [1, 2], [2, 3], [1,2,3]]) =>14

def sum_all(lst):
    pass
```

**Exercise**: 

Write a function find nth that consume a list of number L, and a number target, and a integer produce the index of nth target in the list L, if there is less than nth number of target, the funct should produce -1.
```Python
findnth([1, 2, 1, 3, 1], 1, 3) => 4
findnth([1, 2, 3, 4, 5], 1, 2) => -1
def findnth(lst, ):
    pass
```

**Exercise**: 

Write a function that output stars follow the below patten:
   
```Python
foo(3):
  1 
 222
33333

foo(5):
    1 
   222
  33333
 4444444
555555555
```



