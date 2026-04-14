# **What is a Module in Python?**

A module in Python is a file that contains Python code (functions, classes, variables, or even runnable code) and is used to organize and reuse code efficiently.

* A module is simply a .py file that can be imported and used in other Python programs.

* Modules help keep the code modular, readable, and maintainable.
* Python has built-in modules (like math, random, os) and also allows users to create custom modules.

## **Types of Modules in Python**

### **1. Built-in Modules (Standard Library)**

  * Pre-installed modules in Python.
  * Example: math, random, os, sys

### **Example usage:**

import math
print(math.sqrt(25))  # Output: 5.0

### **2.  User-Defined Modules (Custom Modules)**

  * Any Python file (.py) you create can be used as a module.


### **Example:**

* Create a file called mymodule.py: `(use VSCode/Cursor on local computer)`

def add(a, b):
    return a + b

* Import and use it in another script: `(use VSCode/Cursor on local computer)`

import mymodule
print(mymodule.add(5, 3))  # Output: 8

### **3.  External Modules (Third-party Libraries)**

* Installed via pip (pip install module_name).
* Example: numpy, pandas, requests
* Example usage:


!pip install requests

import requests
response = requests.get("https://www.example.com")
print(response.status_code)

## **How to Import a Module in Python?**

Python provides several ways to import modules:

### **1.  Basic Import**

import math
print(math.pi)  # Output: 3.141592653589793

### **2.  Import with Alias (as)**

import numpy as np
print(np.array([1, 2, 3]))

### **3. Import Specific Functions or Variables (from ... import ...)**



from math import sqrt, pi
print(sqrt(16))  # Output: 4.0
print(pi)        # Output: 3.141592653589793

from math import sqrt as s, pi as p

print(s(16))
print(p )

### **4. Import Everything (from module import *) (Not recommended for large modules)**  

from math import * # wild card
print(sin(0))  # Output: 0.0

# Case 1: 'import math' (Lazy-loading)
import math  # Only loads the module object
# No extra memory used until `math.sqrt()` is called.

# Case 2: 'from math import *' (Eager-loading)
from math import *  # Loads ALL names (pi, sin, cos, sqrt, ...)
# Memory usage increases even if you never use `pi` or `sin`.


## **What’s Happening in This Namespace Overlap?**

You’re executing:

from math import *
from numpy import *
print(pi)  # Which `pi` is being printed? math.pi or numpy.pi?


This is a **classic namespace collision** caused by wildcard imports (`from ... import *`). Here’s what Python does:

## **How Python Resolves the Conflict**

-   `from math import *` → Dumps **all** of `math`’s names (e.g., `pi`, `sin`, `sqrt`) into the global namespace.
-   `from numpy import *` → Dumps **all** of `numpy`’s names into the same namespace, **overwriting any duplicates**.

#### **Which `pi` Wins?**

-   The **last imported `pi`** takes precedence (in this case, `numpy.pi`).
-   So, `print(pi)` will output `numpy.pi` (≈ `3.141592653589793`), **not** `math.pi`.

## **Advantages of Using Modules**

✔ **Code Reusability** – Write once, use anywhere.

✔ **Organization** – Keep related functions together.

✔ **Namespace Management** – Prevents variable conflicts.

✔ **Faster Development** – Use existing libraries instead of writing everything from scratch.

#**Understanding Functions in Python**


A Python function is a block of organized, reusable code that is used to perform a single, related action. Functions provide better modularity for your application and a high degree of code reusing.

# This is a global function because it's defined at the top level of the module.
def my_function():
  print("Hello! World")

# The function can be called from anywhere in the module.
my_function()

A global function in Python is a function that’s defined in the main body of a module, rather than inside another function or class. This means that the function is available throughout the module, and if the module is imported into another file, the function can be accessed from there as well.

## **Key Points:**

### **Scope:**

* Global functions have a module-level scope. They can be called by any code within that module, and if imported, they can be used elsewhere too.

### **Usage:**

* Global functions are typically used to perform tasks that don't depend on a specific object's state. They’re ideal for utility functions, helper functions, or any code that can be reused in various parts of your program.

## **Types of Python Functions**

Python provides the following types of functions −


1)	**Built-in functions**

-   Python's standard library includes number of built-in functions. Some of Python's built-in functions are print(), int(), len(), sum(), etc. These functions are always available, as they are loaded into computer's memory as soon as you start Python interpreter.

2)  **Functions defined in built-in modules**

-   The standard library also bundles a number of modules. Each module defines a group of functions. These functions are not readily available. You need to import them into the memory from their respective modules.

3)  **User-defined functions**

-   In addition to the built-in functions and functions in the built-in modules, you can also create your own functions. These functions are called user-defined functions.

# Built-in functions
print("Hello! World")

# Functions defined in built-in modules
import random
print(random.random())

# User-defined functions
def my_function():
  print("Hello! Operation Badar")

my_function()

## **Syntax to Define a Python Function**

```python
def function_name( parameters ):
   "function_docstring"
   function_suite
   return [expression]
   ```

def greetings():
   "This is docstring of greetings function"
   greet = 'Hello World!'
   return greet

message = greetings()
print(message)

## **Pass by Reference vs Value**

Python uses pass by object reference. Immutable objects (e.g. integers) are unchanged, while mutable objects (e.g. lists) are modified. Examples:
* Integers: `x = 5` remains `5` after modification.
* Lists: `x = [1, 2, 3]` becomes `[1, 2, 3, 4]` after appending `4`.

In this example, `x` remains unchanged after the `modify_value` function, because it's an immutable integer. However, `lst` is modified after the `modify_list` function, because it's a mutable list.

def modify_value(x):
    x = 10
    print("Within function:", x)

# Immutable object (integer)
x = 5
print("Original:", x)
modify_value(x)
print("After function:", x)

def modify_list(lst):
    lst.append(4)
    print("Within function: ", lst, " - ID:", id(lst))

# Mutable object (list)
lst = [1, 2, 3]
print("Original:", lst, " - ID:", id(lst))
modify_list(lst)
print("After function:", lst, " - ID:", id(lst))

## **Function Arguments**

Function arguments are the values or variables passed into a function when it is called.

def greetings(name):
   "This is docstring of greetings function"
   print ("Hello {}".format(name))
   return

greetings("Ali")
greetings("Omar")
greetings("Usman")

## **Keyword Arguments**

Keyword arguments are related to the function calls. When you use keyword arguments in a function call, the caller identifies the arguments by the parameter name. This allows you to skip arguments or place them out of order because the Python interpreter is able to use the keywords provided to match the values with parameters.

def printinfo( name, age ):
   "This prints a passed info into this function"
   print ("Name: ", name)
   print ("Age ", age)
   return;

# Now you can call printinfo function
printinfo( age=50, name="Arif" )
#printinfo(50, "Arif" )

def add(x: int,y: int=0) -> float:
   return float(x + y)

print(float(add(10,20)))

print(add(y=50.0, x=2.0)) # type hints are not enforced in Python

print(add(x=5))

## **\*  unpacking iterables**

In Python, the * operator is used for unpacking iterables (like lists, tuples, or sets) into individual elements. When you use * before a list (or any iterable) in a function call, it unpacks the list and passes its elements as separate positional arguments to the function.

Example:

def my_sum(*nums):
  print(type(nums),", ", nums)

  return sum(nums)

print("Sum     = ", my_sum(1,2,3,4,5,8,5),"\n")
print("Sum *[] = ", my_sum(*[1,2,3,4,5,8,5]), "\n") # *  unpacking list
print("Sum *() = ", my_sum(*(1,2,3,4,5,8,5))) # *  unpacking tuple


## **Default Arguments**

A default argument is an argument that assumes a default value if a value is not provided in the function call for that argument.

def printinfo( name, age = 35 ):
   "This prints a passed info into this function"
   print ("Name: ", name)
   print ("Age ", age)
   return;

# Now you can call printinfo function
printinfo( age=50, name="Arif" )
printinfo( name="Arif" )

## **Positional-only arguments**

Those arguments that can only be specified by their position in the function call is called as `Positional-only arguments`. They are defined by placing a `"/"` in the function's parameter list after all positional-only parameters.

Example

  - In the following example, we have defined two positional-only arguments namely `"x"` and `"y"`. This method should be called with positional arguments in the order in which the arguments are declared, otherwise, we will get an error.

def posFun(x, y, /, z):
    print(x + y + z)

print("Evaluating positional-only arguments: ")
posFun(1, 2, z=3)

# uncomment to see error
#posFun(x=1, y=2, z=3)

# Run to see error
posFun(x=1, y=2, z=3)

## **Error**

```python
posFun(x=1, y=2, z=3)
```

This means that arguments before the '/' must be specified by their position in the function call and cannot be passed using keyword arguments.

`x` and `y` are declared before the '/', making them positional-only. When you call `posFun(x=1, y=2, z=3)`, you're attempting to pass `x` and `y` as keyword arguments, violating this rule and hence the `TypeError` is raised.

## **Keyword-only arguments**

Those arguments that must be specified by their `name` while calling the function is known as `Keyword-only arguments`. They are defined by placing an `asterisk ("*")` in the function's parameter list before any keyword-only parameters. This type of argument can only be passed to a function as a keyword argument, not a positional argument.

def posFun(*, num1, num2, num3):
    print(num1 * num2 * num3)

print("Evaluating keyword-only arguments: ")
posFun(num1=6, num2=8, num3=5)

posFun(num3=6, num1=8, num2=5)


# TypeError: posFun() takes 0 positional arguments but 3 were given
#posFun(6, 8, 5)

## **Arbitrary or Variable-length Arguments**

You may need to process a function for more arguments than you specified while defining the function. These arguments are called variable-length arguments and are not named in the function definition, unlike required and default arguments.

Syntax for a function with non-keyword variable arguments is this −

```python
  def functionname([formal_args,] *var_args_tuple ):
    "function_docstring"
    function_suite
    return [expression]

```

def printinfo( arg1, *vartuple ):
   "This prints a variable passed arguments"
   print ("Output is: ")
   print (arg1)
   for var in vartuple:
      print ("*",var)
   return;

# Now you can call printinfo function
printinfo( 10 )
printinfo( 70, 60, 50, 70, 90 )

## **Python Function with Return Value**

The return keyword as the last statement in function definition indicates end of function block, and the program flow goes back to the calling function. ***`Although reduced indent after the last statement in the block also implies return but using explicit return is a good practice`***.

Along with the flow control, the function can also return value of an expression to the calling function. The value of returned expression can be stored in a variable for further processing.

def add(x,y):
   z=x+y
   return z

a=10
b=20
result = add(a,b)

print ("a = {} b = {} a+b = {}".format(a, b, result))

## **The Anonymous Functions**

The functions are called anonymous when they are not declared in the standard manner by using the def keyword. Instead, they are defined using the `lambda keyword`.

### **Syntax**

The syntax of lambda functions contains only a single statement, which is as follows −

```python
lambda [arg1 [,arg2,.....argn]]:expression
```

def add_two(x, y):
  return x + y

my_lambda = lambda x, y:  x + y;

print(my_lambda(1,2))

# prompt: sort by value dictionary using lambda function

my_dict = {"apple": 5, "banana": 2, "cherry": 8, "date": 1}

sorted_dict = dict(sorted(my_dict.items(), key=lambda item: item[1]))

sorted_dict

# Function definition is here
sum = lambda arg1, arg2: arg1 + arg2;

# Now you can call sum as a function
print ("Value of total : ", sum( 10, 20 ))
print ("Value of total : ", sum( 50, 20 ))

## **Scope of Variables**

All variables in a program may not be accessible at all locations in that program. This depends on where you have declared a variable.

The scope of a variable determines the portion of the program where you can access a particular identifier. There are two basic scopes of variables in Python −

  - `Global variables`

  - `Local variables`


**Global vs. Local variables**

Variables that are defined inside a function body have a local scope, and those defined outside have a global scope.

This means that local variables can be accessed only inside the function in which they are declared, whereas global variables can be accessed throughout the program body by all functions. When you call a function, the variables declared inside it are brought into scope.

total = 0; # This is global variable.
# Function definition is here
def sum( arg1, arg2 ):
   # Add both the parameters and return them."
   total = arg1 + arg2; # Here total is local variable.
   print ("Inside the function local total : ", total)
   return total;

# Now you can call sum function
sum( 10, 20 );
print ("Outside the function global total : ", total)

##**Arbitrary Keyword Arguments, **kwargs**

If you do not know how many keyword arguments that will be passed into your function, add two asterisk: ** before the parameter name in the function definition.

This way the function will receive a dictionary of arguments, and can access the items accordingly:



def my_function(**student):
  print("\nHis last name is " + student["lname"])

  for key, value in student.items():
    print(key, value)

  print(student)

my_function(fname = "Ali", lname = "Osman")

my_function(fname = "Ali", lname = "Osman", course = "Python - 101", day="Saturday", time="1400 - 1800")

my_dict = {"fname": "Arif", "lname": "Rozani", "course":"101 - 201", "day":"Saturday | Sunday", "role":"Student"}

#my_function(my_dict) # uncomment to see TypeError
my_function(**my_dict) # use ** to unpack the dictionary

##**Generator Function**

A generator function in Python is a special type of function that allows you to iterate over a sequence of values `without storing the entire sequence in memory`. **Instead of returning a single value using return, a generator function uses the `yield` keyword to produce a series of values, `one at a time`, `on-the-fly`**. This makes generator functions highly `memory-efficient` for working with `large` or `infinite sequences`.

## **Key Features of Generator Functions**

1. **Lazy Evaluation**: Values are generated only when needed, not all at once.

2.  **Memory Efficiency**: Only one value is stored in memory at a time.
3.  **Iterable**: Generator functions return a generator object, which can be iterated over using a for loop or functions like next().
4.  **Resumable**: The state of the generator function is saved between yield calls, allowing it to resume execution from where it left off.

## **Syntax of a Generator Function**

A generator function is defined like a normal function but uses the yield keyword instead of return.

```python
def generator_function():
    yield value

```

## **How Generator Functions Work**

1.  When a generator function is called, it returns a generator object without executing the function body.

2.  The function body executes only when the generator object is iterated over (e.g., using a for loop or next()).
3.  When the yield statement is encountered, the function pauses and returns the yielded value. The function’s state (e.g., local variables) is saved.
4.  The function resumes execution from where it left off the next time next() is called or the generator is iterated over.

### **Example 1: Simple Generator Function**

def simple_generator():
    yield 1
    yield 2
    yield 3

# Create a generator object
gen = simple_generator()

print(gen, " : ", type(gen))

# Iterate over the generator
for value in gen:
    print(value, " : ", type(value))

## **Lets produce an error:**

**Once the generator is exhausted, calling next() will raise a StopIteration exception.**

print(next(gen)) #error: StopIteration

### **Example 2: Infinite Sequence**

Generators are useful for generating infinite sequences since they don’t store all values in memory.

### **How It Works:**

1.  infinite_sequence():
    * This function starts with num = 0.

    * Inside an infinite while True loop, it yields num and then increments it by 1.
    * Since yield pauses execution, it remembers the state and resumes from there when next() is called.

2.  Creating the Generator:

    * gen = infinite_sequence() initializes the generator.
    

3.  Printing First 5 Numbers:

    * Using next(gen), we retrieve values from the generator five times inside a loop.

    * The next time we call next(gen), execution resumes from where it left off.

def infinite_sequence():
    num = 0
    while True:
        yield num # Since yield pauses execution, it remembers the state and resumes from there when next() is called.
        num += 1

# Create a generator object
gen = infinite_sequence() #initializes the generator.

# Print the first 5 numbers, _ is a throw away variable
for _ in range(5):
    print(next(gen)) # The next time we call next(gen), execution resumes from where it left off.

def infinite_loop(): #without yield it become infinite
   num = 0
   while True:
       #yield num   # with yield it become generator without yield its a infinite loop
       num += 1
       print("infinite_loop() : num = ", num)

infinite_loop()

## **Generator Expressions**
Generator expressions are a concise way to create generators. They are similar to list comprehensions but use parentheses instead of square brackets.

Example:

# Generator expression
gen = (x * x for x in range(5))
print(type(gen))

# Iterate over the generator
for value in gen:
    print(value, " : ", type(value))

##**Recursive Function in Python**

A **recursive function** is a function that calls itself during its execution. It breaks down a problem into smaller, more manageable subproblems, solving each one recursively until a **base case** is reached. The base case is the condition that stops the recursion, preventing infinite loops.


## **Key Components of a Recursive Function**

*   **Base Case**: The condition that stops the recursion.
*   **Recursive Case**: The part of the function where it calls itself with a modified input.

## **Example: Factorial of a Number**

The factorial of a number n (denoted as n!) is the product of all positive integers from 1 to n. It can be defined recursively as:

-   n! = n * (n-1)! (Recursive Case)
-   0! = 1 (Base Case)

def factorial(n):
    # Base case
    if n == 0:
        return 1
    # Recursive case
    else:
        return n * factorial(n - 1)

# Example usage
print(factorial(5))  # Output: 120

**How It Works**

1.  factorial(5) calls factorial(4).
2.  factorial(4) calls factorial(3).
3.  This continues until factorial(0) is called, which returns 1.
4.  The results are propagated back up the chain:
  -   1 * 1 = 1
  -   2 * 1 = 2
  -   3 * 2 = 6
  -   4 * 6 = 24
  -   5 * 24 = 120

## **Example: Fibonacci Sequence**

The Fibonacci sequence is a series of numbers where each number is the sum of the two preceding ones: 0, 1, 1, 2, 3, 5, 8, 13, ...

def fibonacci(n):
    # Base cases
    if n == 0:
        return 0
    elif n == 1:
        return 1
    # Recursive case
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

# Example usage
print(fibonacci(6))  # Output: 8

## **Advantages of Recursive Functions**

1.    Simplifies Code: Breaks complex problems into smaller, easier-to-understand parts.
2.    Elegant Solutions: Often provides a clean and concise solution for problems like tree traversals, sorting, and mathematical computations.
3.    Natural Fit for Certain Problems: Works well for problems with recursive structures (e.g., factorial, Fibonacci, tree traversals).

## **Disadvantages of Recursive Functions**

*   Stack Overflow: Deep recursion can lead to a stack overflow if the base case is not reached.
*   Performance Issues: Recursive functions can be slower and use more memory compared to iterative solutions due to repeated function calls.
*   Debugging Complexity: Recursive logic can be harder to debug and trace.

## **When to Use Recursive Functions**

* When the problem can be naturally divided into smaller subproblems.
* When the depth of recursion is limited and won’t cause stack overflow.
* For problems like tree traversals, divide-and-conquer algorithms, or mathematical sequences.

# prompt: generate an example of recursive function

def factorial(n):
  if n == 0:
    return 1
  else:
    return n * factorial(n-1)

number = 5
result = factorial(number)
print(f"The factorial of {number} is {result}")

## **Multi Type Return in Function**


In Python, a function can return multiple values of different types by packaging them into a tuple, list, dictionary, or even a custom object. This is often referred to as a multi-type return. For example, a function can return an int, a list, and a dict together, providing flexibility in handling complex data. Type annotations (e.g., Tuple[int, List[str], Dict[str, int]]) can be used to specify the expected return types, making the code more readable and maintainable. Multi-type returns are useful when a function needs to provide diverse outputs, such as a status code, a list of results, and a dictionary of metadata, all in a single call.

def example_function(a: int, b: int = 0, *args: float, **kwargs: str) -> Tuple[int, List[float], Dict[str, str]]:
    """Example function demonstrating various parameter types.
    Args:
        a: An integer.
        b: An integer with a default value of 0.
        *args: Variable-length positional arguments of type float.
        **kwargs: Variable-length keyword arguments of type string.
    Returns:
        A tuple containing:
        - The sum of 'a' and 'b'.
        - A list of the variable-length positional arguments ('args').
        - A dictionary of the variable-length keyword arguments ('kwargs').
    """
    sum_ab = a + b
    args_list = list(args)  # Convert tuple to a list
    return sum_ab, args_list, kwargs

# Example usage
result = example_function(1, 2, 3.14, 2.71, name="Alice", city="New York")
print(result)

result = example_function(10, *[1.0, 2.0, 3.0], **{"country": "USA", "language": "English"})
result


## 🧭 **Python’s Precedence Rules for Name Resolution**

This is based on something called the **LEGB rule** — it defines the order in which Python looks for **names** (variables, functions, etc.).

### 🧱 L → Local

-   Inside the current function or method.
    

### 🧱 E → Enclosing

-   Functions inside other functions (closures).
    

### 🧱 G → Global

-   Top-level of the script/module.
    

### 🧱 B → Built-in

-   Python’s built-in names like `len`, `sum`, etc.

## **🌟 Full LEGB Precedence Example in One Go:**

from math import *

print("Math: pi           = ", pi)

pi = 1
print("Global: pi         = ", pi)

class MyClass:
  pi = 2
  print("MyClass: pi        = ",pi)

  def my_function():
    pi = 3
    print("my_function: pi    = ",pi)

    def inner_function():
      pi = 4
      print("inner_function: pi = ",pi)


    inner_function()

  my_function()

### **🧨 Want to Go One Step Deeper? Let’s Add `global` and `nonlocal`**

Let’s modify variables across scopes:

# This is a GLOBAL variable


# Call the outer function
webpage()

# Check the global total_clicks value
print("After webpage(), total_clicks:", total_clicks)
