# Agentic AI - Python - Lesson 05 - Control Flow & Loops.ipynb

# **Tutorial: Control Flow and Decision Making in Python**

## **1. Introduction to Control Flow**

Control flow refers to the order in which statements are executed in a program. In Python, decision-making is achieved using if, elif, and else statements, along with comparison and logical operators.

## **2. Comparison Operators**

Comparison operators are used to compare values and return True or False. Here are the most common ones:

* == (equal to)
* != &nbsp;(not equal to)
* \> &nbsp;&nbsp;(greater than)
* < &nbsp;&nbsp;(less than)
* \>= (greater than or equal to)
* <= (less than or equal to)

<br>

Example Code:
"""

x: int = 10
y: int = 20

print("x == y = ", x == y)  # False
print("x != y = ", x != y)  # True
print("x > y  = ", x > y)   # False
print("x < y  = ", x < y)   # True
print("x >= y = ", x >= y)  # False
print("x <= y = ", x <= y)  # True

"""# **3. Logical Operators**


Logical operators combine multiple conditions:

* and (True if both conditions are True)
* or (True if at least one condition is True)
* not (reverses the result of a condition)
"""

age: int = 25
is_student: bool = True

# Check if age is greater than 18 AND is_student is True
if age > 18 and is_student:
    print("You are eligible for a student discount.")

# Check if age is less than 12 OR greater than 60
if age < 12 or age > 60:
    print("You qualify for a special discount.")

# Check if the person is NOT a student
if not is_student:
    print("You are not a student.")

"""# **4. The if Statement**

The if statement is used to execute a block of code only if a condition is True.

<br>

Example Code:
"""

num: int = 10

if num > 0:
    print("The number is positive.")

"""# **5. The else Statement**

The else statement is used to execute a block of code if the if condition is False.

<br>

Example Code:
"""

num: int = -5

if num > 0:
    print("The number is positive.")
else:
    print("The number is not positive.")

"""# **6. The elif Statement**

The elif statement is used to check multiple conditions. It stands for "else if."
<br>

Example Code:
"""

num: int = 0

if num > 0: # Program execution step# 1 if condition = False
    print("The number is positive.")
elif num < 0: # Program execution step# 2 if condition = False
    print("The number is negative.")
else: # Program execution step# 3 python will execute the else block
    print("The number is zero.")

"""# **7. Nested if Statements**

if statements can be nested inside other if statements to check multiple conditions.

<br>

Example Code:
"""

num: int = 10
#num: int = -10

if num > 0: # check wather the number is positive or negative

    if num % 2 == 0: # Modulus operator, remainder 0 = even_number,
        print("The number is positive and even.")
    else: # remainder 1 = odd_number,
        print("The number is positive and odd.")

else:
    print("The number is negative.")

"""# **8. Practical Examples**

Here are two practical examples to solidify these concepts.

Example 1: Simple Calculator
"""

operation: str = input("Enter the operation (+, -, *, /): ")
num1: float = float(input("Enter the first number: "))
num2: float = float(input("Enter the second number: "))

if operation == '+':
    result = num1 + num2
elif operation == '-':
    result = num1 - num2
elif operation == '*':
    result = num1 * num2
elif operation == '/':
    if num2 != 0:
        result = num1 / num2
    else:
        result = "Error: Division by zero."
else:
    result = "Invalid operation."

print("Result:", result)

"""<font color="#a83285" size=5> From now onwards you will be seeing the power of Generative AI in our tutorial </font>"""

# prompt: build a calculator which takes input from the user, beside basic functionality include modulus, floor division, Exponentiation

def calculator():
  """
  A calculator function that takes user input for numbers and operations,
  including modulus, floor division, and exponentiation.
  """
  while True:
    operation = input("Enter the operation (+, -, *, /, %, //, ** or 'q' to quit): ")
    if operation.lower() == 'q':
      break
    if operation not in ('+', '-', '*', '/', '%', '//', '**'):
      print("Invalid operation.")
      continue

    try:
      num1 = float(input("Enter the first number: "))
      num2 = float(input("Enter the second number: "))
    except ValueError:
      print("Invalid input. Please enter numbers only.")
      continue

    if operation == '+':
      result = num1 + num2
    elif operation == '-':
      result = num1 - num2
    elif operation == '*':
      result = num1 * num2
    elif operation == '/':
      if num2 != 0:
        result = num1 / num2
      else:
        result = "Error: Division by zero."
        print(result)
        continue
    elif operation == '%':
      result = num1 % num2
    elif operation == '//':
      if num2 != 0:
        result = num1 // num2
      else:
        result = "Error: Division by zero."
        print(result)
        continue
    elif operation == '**':
      result = num1 ** num2

    print("Result:", result)

calculator()

# prompt: generate a grading system for school which takes marks as an  input show grade according to the marks

def grading_system(marks):
  """
  This function takes marks as input and returns the corresponding grade.

  Args:
    marks: The marks obtained by the student.

  Returns:
    The grade corresponding to the marks.
  """
  if marks >= 90:
    grade = "A+"
  elif marks >= 80:
    grade = "A"
  elif marks >= 70:
    grade = "B"
  elif marks >= 60:
    grade = "C"
  elif marks >= 50:
    grade = "D"
  else:
    grade = "F"
  return grade

# Get marks as input from the user
while True:
  try:
    marks = float(input("Enter the marks: "))
    if 0 <= marks <= 100:
      break
    else:
      print("Marks must be between 0 and 100.")
  except ValueError:
    print("Invalid input. Please enter a number.")

# Determine the grade
grade = grading_system(marks)

# Print the grade
print(f"The grade for {marks} marks is: {grade}")

"""## **Python `match-case` Statement**

Python introduced the `match-case` statement in **Python 3.10** as a way to implement **structural pattern matching**, which provides a cleaner and more readable alternative to traditional `if-elif-else` chains.

---

## **1. Basic Syntax**
The `match-case` statement works by comparing an expression against multiple patterns. The syntax is:
"""

def check_status(code):
    match code:
        case 200:
            print("OK")
        case 400:
            print("Bad Request")
        case 404:
            print("Not Found")
        case _:
            print("Unknown Status")

check_status(200)  # Output: OK
check_status(404)  # Output: Not Found
check_status(500)  # Output: Unknown Status

"""[See appendix for more detail on match-case](https://github.com/panaversity/learn-modern-ai-python/blob/main/00_python_colab/Appendix/The%20%60match-case%60%20Statement.md)

# **Tutorial: Loops and Iteration in Python**

## **1. Introduction to Loops**

Loops are used to repeat a block of code multiple times. Python supports two types of loops:

* for loops: Used to iterate over a sequence (e.g., lists, strings, or ranges).
* while loops: Used to repeat a block of code as long as a condition is True.

When to use scenario:

  **A. For Loop:**

  - **`Grading a class of students`**: You have a `list of 30 students` and you want to calculate the average score for each student. You use a `for` loop to iterate over the list of students and calculate the average score for each one.

  - Washing Machine(number spins), Microwave Oven e.t.c.

**B. While Loop:**

  - **`Filling up a gas tank`**: You want to fill up your gas tank `until it's full.` You don't know how many times you'll need to fill up the tank, but you'll keep filling it up until it's full. You use a `while` loop to fill up the tank until it's full.

  - Air Conditioner, Refigrator, Heater, Washing Machine(filling water) e.t.c.

## **2. The for Loop**

The for loop iterates over a sequence (like a list, string, or range) and executes a block of code for each item `for a specified or fixed number of times`.

Example Code:
"""

# Iterate over a list
fruits: list = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Note: Membership Operators in Python in, not in

# Iterate over a string
word: str = "Python"
for letter in word:
    print(letter)

"""## **for Loop with else in Python**

In Python, a for loop can have an else block. The else block runs only if the loop completes without a break statement.

*(Contributor: Daniel Hashmi from Karachi)*

## **Example 1: for loop with else (No break)**
"""

numbers = [1, 2, 3, 4, 5]

for num in numbers:
    print(num)
else:
    print("Loop completed successfully!")

"""## **Example 2: for loop with break (Skipping else)**"""

numbers = [1, 2, 3, 4, 5]

for num in numbers:
    print(num)
    if num == 3:
        print("Breaking the loop!")
        break
else:
    print("Loop completed successfully!")  # This will NOT run

"""## **Example 3: Searching with else**"""

numbers = [1, 2, 3, 4, 5]

for num in numbers:
    if num == 6:
        print("Number found!")
        break
else:
    print("Number not found!")  # Runs because 6 is not in the list

"""<font color="Green" size=3> In Lesson 01 we learned about range() </font>"""

# Print numbers from 0 to 4
for i in range(5):
    print(i)

# Print even numbers from 2 to 10
for i in range(2, 11, 2):
    print(i)

"""`_` (*underscore*) This is a **`throwaway variable`**, which is a common Python convention for a variable that you **`don't plan to use`**. In this case, the loop variable is not used within the loop, so it's assigned to `_`.

If you want to use the loop variable, you can replace `_` with a more meaningful variable name. For example:
"""

for _ in range(10): # Just to show that _ is a loop variable, but its throwaway variable
    # Code to be executed 100,000 times
    print(f"Hello, World! Iteration { _ }")

"""## **3. The while Loop**

The while loop repeats a block of code `as long as a condition is True.`

<br>

Example Code:
"""

# Print numbers from 1 to 5
count: int = 1
while count <= 5:
    print(count)
    count += 1

"""## **4. Controlling Loops**

Python provides two keywords (`break` & `continue`) to control loops:

* **break**: `Exits` the loop immediately.
* **continue**: `Skips` the rest of the code in the current iteration and moves to the next iteration.

<br>


Example Code:
"""

# Break example
for i in range(10):
    if i == 5:
        break
    print(i)  # Prints 0, 1, 2, 3, 4

# Continue example
for i in range(5):
    if i == 3:
        continue
    print(i)  # Prints 0, 1, 2, 4

"""## **5. Nested Loops**

### **What are nested loops?**

Nested loops, also known as inner loops or nested iterations, refer to the process of placing one loop inside another loop. The inner loop will iterate through its entire cycle for each iteration of the outer loop.

<br>


### **Example Code:**
"""

# Multiplication table
for outer in range(1, 6): # outer loop
    print(f"Multiplication table for {outer}:")
    for inner in range(1, 6): # nested inner loop
        print(f"{outer} * {inner} = {outer * inner}")
    print()  # Add a blank line after each row

"""**Use Cases for Nested Loops**

Nested loops are useful in various scenarios, such as:

1. **Matrix operations**: When working with matrices, you often need to iterate over each element in a two-dimensional array. Nested loops can help you achieve this.

2. **Iterating over multiple lists**: If you have multiple lists and want to perform operations on each combination of elements, nested loops can be used.
3. **Games and simulations**: Nested loops can be used to create game boards, simulate complex systems, or iterate over multiple levels of data.
4. **Data processing**: When dealing with large datasets, nested loops can help you process and analyze the data by iterating over each element and performing operations.

**Best Practices for Using Nested Loops**

While nested loops can be powerful, it's essential to use them wisely to avoid performance issues and improve readability:

1. **Minimize nesting**: Try to limit the number of nested loops to three levels or less, as excessive nesting can lead to performance degradation and decreased readability.

2. **Use meaningful variable names**: Use clear and descriptive variable names to help distinguish between the outer and inner loops.
3. **Optimize loop conditions**: Ensure that the loop conditions are optimized to minimize unnecessary iterations.

## **6. Practical Examples**

Here are two practical examples to solidify these concepts.

<br>

**Example 1**: Sum of Numbers
"""

# Sum numbers from 1 to 100
total: int = 0
for i in range(1, 101):
    total += i
print("Sum of numbers from 1 to 100:", total)

"""**Example 2**: Finding Factors of a Number"""

# Find factors of a number
num: int = 24
factors = []
for i in range(1, num + 1):
    if num % i == 0:
        factors.append(i)
print(f"Factors of {num}: {factors}")