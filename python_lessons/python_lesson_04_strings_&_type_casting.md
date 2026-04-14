# Agentic AI - Python - Lesson 04 - Strings & Type Casting.ipynb

**Strings in Python**

In Python, a string is a sequence of characters enclosed in quotes (either single, double, or triple quotes). Strings are `immutable`, meaning they cannot be changed after they are created.

**Creating Strings**

There are several ways to create strings in Python:

1. **Single Quotes**: `my_string = 'Hello, World!'`
2. **Double Quotes**: `my_string = "Hello, World!"`
3. **Triple Quotes**: `my_string = '''Hello, World!'''` (can span multiple lines)
4. **Raw Strings**: `my_string = r'Hello, World!'` (treats backslashes as literal characters)
"""

#for multi line string use triple quotes '''any string'''
my_string: str = '''Hello,
World!'''
print(my_string)

my_string: str = r'Hello\t,\n Worl\\d!'
print(my_string)

print("\n-----\n")

my_string = 'Hello,\n World!'
print(my_string)

"""**Escape Sequence Characters in Python**
======================================

In Python, escape sequence characters are used to represent special characters that have a specific meaning in a string. These characters are denoted by a backslash (`\`) followed by a character.

"""

print("Hello,\b World!") #\b backspace
print("Hello,\tWorld!")  #\t tab
print("Hello, \"World!\"")
print("Hello,\\ World!")

"""### **Unicode characters**


Python also supports Unicode escape sequence characters, which are used to represent `Unicode characters`. These characters are denoted by `\u` followed by a four-digit hexadecimal code.
"""

print(r"\u0041 = ", "\u0041")
print(r"\u0042 = ", "\u0042")
print(r"\u0043 = ", "\u0043")

"""### **Performing Differrent Operations on String Object**

| S# | Operation         | Example                                                                           |
|----|-------------------|-----------------------------------------------------------------------------------|
| 1  | **Concatenation** | `my_string = 'Hello, ' + 'World!'`                                                |
| 2  | **Indexing**      | `my_string = 'Hello, World!'; print(my_string[0])  # prints 'H'`                  |
| 3  | **Slicing**       | `my_string = 'Hello, World!'; print(my_string[7:])  # prints 'World!'`            |
| 4  | **Length**        | `my_string = 'Hello, World!'; print(len(my_string))  # prints 13`                 |
| 5  |  **Upper Case**   | `my_string = 'Hello, World!'; print(my_string.upper())  # prints 'HELLO, WORLD!'` |
| 6  | **Lower Case**    | `my_string = 'Hello, World!'; print(my_string.lower())  # prints 'hello, world!'` |
"""

my_string = 'Hello, ' + 'World!' #Concatenation using + sign
print(my_string)

#Indexing, index value starts with 0 zero, so  the first character
#have index vlaue 0, second character have index value 1 and the third one
#have index value 2 and so on.
print(my_string[1]) #It will print 'e'

my_string: str = 'Hello, World!'
print(my_string[7:]) #It starts from 7 till the end of the string
print(my_string[0:5]) #It starts from 0 till the index 4 - (0,1,2,3,4) = 5 characters

print(len(" Hello, World! "))#calculating length of a string even the space will be treated as character

print(my_string.upper()) #Upper Case
print(my_string.lower()) #Lower Case

"""Here are some commonly used string methods:

1. **`split()`**: splits a string into a list of substrings based on a delimiter
2. **`join()`**: joins a list of strings into a single string
3. **`replace()`**: replaces a substring with another substring
4. **`find()`**: returns the index of a substring
5. **`count()`**: returns the number of occurrences of a substring
"""

my_string: str = 'Hello! World'

# split into a list of words
words: str = my_string.split()
print("my_string.split()    = ", words)

words = my_string.split(" ") # Space as a delimiter
print('my_string.split(" ") = ',words)

words = my_string.split("l") # Splitting using 'l' as the delimiter
print('my_string.split("l") = ', words)

"""**Steps of Execution:**

- The split("l") method breaks the string "Hello! World" wherever the letter l appears.

<br>

After splitting, the parts are:

<br>

**Before the first l**:
- "He" Between the first and second l: "" (empty string, as there’s no character between the two ls)

<br>

**After the second l**: "o! Wor"

- The resulting list is: ["He", "", "o!, Wor", "d"].

<br>

**Output:**
"""

words: str = my_string.split("l") # Splitting using 'l' as the delimiter
print(words)

"""The argument of join() is the iterable, and the my_string acts as a separator that is placed between the elements of the iterable.

my_string = '`, `'

The variable my_string is assigned the value '`, `'. This string (`comma followed by a space`) will be used as the `separator` for joining elements of a list.
"""

# join the words back into a single string
my_string: str = ', '
joined_string: str = my_string.join(['Pakistan', 'USA', 'Canada', 'France', 'Japan'])
print(joined_string)  # Pakistan, USA, Canada, France, Japan

joined_string: str = my_string.join('Pakistan') # my_string works as a seprator for each character in the word 'Pakistan', because string is a sequence of caharacter

print(joined_string) # P, a, k, i, s, t, a, n

print('-'.join(['Apple', 'Banana', 'Cherry'])); # ; The line terminitor

my_string: str = "Hello, World! Hello, Pakistan"
# replace a substring
my_string = my_string.replace('Hello', 'Salam Walikum')
print(my_string)  # prints 'Salam Walikum, World! Salam Walikum, Pakistan'

my_string: str = "Hello, World! Hello, Pakistan"
# find the index of a substring
starting_index = my_string.find('Hello') # Index value of the first occurance of the word 'Hello'
print("starting_index = ", starting_index)  # prints 0

# Now lets find the second occurance of the word 'Hello'
# index value start from zero

starting_index2: str = starting_index + len("Hello") #len=5

print(my_string[starting_index2:] ) # after slicing ", World! Hello, Pakistan
print(my_string[starting_index2:].find("Hello")) # Starting index 9, because of slicing ", World! Hello, Pakistan"

print(my_string)
print(len(my_string)) #character count = 29

print('\n-----\n')

print("Substring to search    = ", "Hello")
print("Starting index         = ", len("Hello")) # 5
print("End index              = ", len(my_string))
print("Second Occurance index = ", my_string.index(("Hello"), len("Hello"), len(my_string))) # (substring, start, end) - print 14

#Uncomment to see ValueError: substring not found
#print("Second Occurance index = ", my_string.index(("Hello7"), len("Hello"), len(my_string))) # (substring, start, end)

print(my_string.find("Hello7")) # -1 for not found

"""## Conclusion
-  index() → Finds substring, raises error if not found.
-  find() → Finds substring, returns -1 if not found (safer).
-  Can specify start and end positions for more control.
-  Use a loop if you need all occurrences of a substring.
"""

my_string = "Hello, World! Hello, Pakistan"
# count the occurrences of a substring
count = my_string.count('Hello')
print("my_string.count('Hello') = ", count)  # prints 2

# count the occurrences of a substring
count = my_string.count('P')
print("my_string.count('P')     = ", count)  # prints 1

# count the occurrences of a substring
count = my_string.count('o')
print("my_string.count('o')     = ", count)  # prints 2

# count the occurrences of a substring
count = my_string.count('hello') # case sensitive
print("my_string.count('hello') = ", count)  # prints 0

"""**String Formatting**
-------------------

Python provides several ways to format strings:

1. **`%` Operator**: `my_string = 'Hello, %s!' % 'World'`
  * In Python, `%s`, `%d`, `%c`, `%f` are placeholders for values in a string. They are used with the `%` operator to insert values into a string.
  * **Note**: The `%` operator is an older way of formatting strings in Python. The newer and more recommended way is to use the `str.format()` method or f-strings (introduced in Python 3.6). For example:
2. **`str.format()`**: `my_string = 'Hello, {}!'.format('World')`
3. **f-Strings**: `my_string = f'Hello, {"World"}!'`


<br>

| Placeholder | Meaning                              | Example                                |
|-------------|--------------------------------------|----------------------------------------|
| %s          | String                               | "Hello, %s" % "Alice" → "Hello, Alice" |
| %d          | Integer (Decimal)                    | "Age: %d" % 25 → "Age: 25"             |
| %c          | Character                            | "Letter: %c" % 'A' → "Letter: A"       |
| %f          | Floating-point                       | "Pi: %f" % 3.14159 → "Pi: 3.141590"    |
| %.nf        | Floating-point with n decimal places | "%.2f" % 3.14159 → "3.14"              |

## **% Operator**
"""

name: str = 'John'
age: int = 20
first_letter: str = name[0]
my_weight: float = 70.532000 # 70.536000

#uncomment to see type
#print(type((name, first_letter, age, my_weight)))

# using % operator
my_string: str = '''My name is %s, first letter of my name is \'%c\', I am %d years old and my weight id %f Kg.''' % (name, first_letter, age, my_weight)
print(my_string)

my_string = '''My name is %s, first letter of my name is \'%c\', I am %d years old and my weight id %.2f Kg.''' % (name, first_letter, age, my_weight) # Dont forget period %.2f
print(my_string)

"""## **String Formatting in Python – Does Order Matter?**

**Yes**, order matters when using string formatting in Python, especially with the % operator, .format(), and f-strings (f""). Let's break it down:
"""

# Error: TypeError: %d format: a real number is required, not str
my_string: str = '''My name is %s, first letter of my name is \'%c\', I am %d years old and my weight id %f Kg.''' % (my_weight, age, name, first_letter)

"""## **str.format()**"""

# using str.format()
my_string: str = 'My name is {} and I am {} years old.'.format(age, name) #order matters
print("line 1: ",my_string)

my_string: str = 'My name is {1} and I am {0} years old.'.format(age, name) #use indexing
print("line 2: ",my_string)

"""## **F-String**"""

# using f-strings
my_string: str = f'My name is {name} and I am {age} years old.' #Using Named Placeholders (Best for Readability)
print("line 3: ",my_string)

my_string: str = fr'My \name is {name} and I am {age}\n \t years \old.' #At the same time it could be f and r as well
print("line 4: ",my_string)

"""**Pool of String Literals in Python**
=====================================

In Python, a pool of string literals is a mechanism used by the interpreter to manage memory allocation for string objects. When a string literal is encountered in the code, Python checks if an identical string already exists in memory. If it does, the new string is not created, and instead, a reference to the existing string is used.

**How it Works**
---------------

When Python encounters a string literal, it checks the following:

1. **`Interning`**: Python checks if the string is already interned, meaning it has been created and stored in memory before. If it is, Python returns a reference to the existing string.
2. **`String Literal Pool`**: If the string is not interned, Python checks the string literal pool, which is a cache(Pronunciation: `kash`) of recently created strings. If the string is found in the pool, Python returns a reference to the existing string.
3. **`Create New String`**: If the string is not found in the pool or interned, Python creates a new string object and stores it in memory.

**Benefits**
------------

The pool of string literals provides several benefits:

* **`Memory Efficiency`**: By reusing existing strings, Python reduces memory allocation and deallocation overhead.
* **`Performance`**: Looking up strings in the pool is faster than creating new strings.
* **`Internalization`**: The pool helps to internalize strings, making them more efficient to use in comparisons and other operations.

"""

a: str = "hello"
b: str = "hello"

#Both variable a and b have same id.
print(id(a))
print(id(b))

c: str = a +"" # Nothing happen because we are appending a empty string.
print(id(c))

c: str = a +" " # A new string object is created in the pool.
print(id(c))

"""## **Interning in Python**

### **1.  What is Interning?**

Interning is a process where Python stores only one copy of certain strings in memory and reuses them whenever the same string is used again. This is done to save memory and speed up comparisons.

### **2. Which Strings are Interned?**

* **Short strings**: Usually strings that are **`20 characters or fewer`**.
* **Identifiers**: Strings that look like variable names (e.g., "x", "my_var").
* **Explicit interning**: You can manually intern a string using the sys.intern() function.

### **3. Example of Manual Interning:**
"""

import sys
a = sys.intern("hello world!")
b = sys.intern("hello world!")
print(a is b)  # True (manually interned)

"""## **String Literal Pool in Python**

### **1.  What is the String Literal Pool?**

The string literal pool is a cache of string literals that appear in the code. When Python encounters a string literal (e.g., "hello"), it checks the pool to see if the string already exists. If it does, Python reuses the existing string instead of creating a new one.

### **2. How Does It Work?**

* **The pool is used for string literals explicitly written in the code** (e.g., "hello", "world").
* **It does not apply to dynamically created strings** (e.g., "hello" + "world").

### **3. Example of String Literal Pool:**
"""

a = "hello"
b = "hello"
print(a is b)  # True (both refer to the same string in the pool)

"""## **String Interning vs String Pool:**

String interning and string pool are two concepts that are often confused with each other, but they are not exactly the same thing.

### **String Interning:**

String interning is a process where the **`compiler or interpreter`** checks if a string already exists in memory before creating a new one. If the string already exists, the compiler or interpreter returns a reference to the existing string instead of creating a new one. This process is also known as "string caching" or "string sharing".

### **String Pool:**

A string pool, on the other hand, is a memory space where all the strings in a program are stored. When a string is created, it is added to the string pool. The string pool is used to manage the memory for string objects.

### **Here are the key differences between string interning and string pool:**

1. **Scope:** String interning is a process that can be applied to **`any type of object`**, **`not just strings`**. String pool, on the other hand, is a memory space specifically designed for strings.

2. **Purpose:** The purpose of string interning is to optimize memory usage by avoiding duplicate objects. The purpose of a string pool is to manage the memory for string objects.

3. **Implementation:** String interning can be implemented using a hash table or a dictionary, where the keys are the strings and the values are the corresponding string objects. A string pool, on the other hand, is typically implemented as a contiguous block of memory where all the strings are stored.

4. **Behavior:** String interning can be enabled or disabled depending on the language or framework. A string pool, on the other hand, is typically always enabled for strings.

<br>

### **Process = Interning**
### **Memory Space = Pool of String Litrels**

## **When Are Strings Not Interned or Pooled?**

1.  **Long Strings**: Strings longer than **`20 characters`** are usually not interned automatically.
"""

a = "this is a very long string"
b = "this is a very long string"
print(a is b)  # False (not interned)
print("id(a)", id(a))
print("id(b)", id(b))

import sys

a = sys.intern("this is a very long string")
b = sys.intern("this is a very long string")

print(a is b)  # True (manually interned)
print("id(a)", id(a))
print("id(b)", id(b))

"""2. **Dynamically Created Strings**: Strings created at runtime (e.g., concatenation) are not interned or pooled."""

a = "hello"
b = "world"
c = a + b  # Dynamically created string
d = "helloworld"
print("c is d = ", c is d)  # False (not interned or pooled)
print(c, " - id(c)", id(c))
print(d, " - id(d)", id(d))

c1 = a + b
print("c is c1 = ",  c is c1)

print(c1, " - id(c1)", id(c1))
print(c,  " - id(c) ", id(c))

print("is contant same = ", c == c1)

# prompt: print list of str functions using dir(), dont show function starting with"__"

# Get the list of string methods
string_methods: str = dir(str)

# Filter out methods starting with "__"
filtered_methods: str = [method for method in string_methods if not method.startswith("__")]

# Print the filtered list
filtered_methods

"""## **String Repetition**

String repetition in Python is a straightforward way to create a new string by concatenating multiple copies of an existing string. You achieve this using the asterisk (`*`) operator.

Here's a concise breakdown:

-   **The Basics:**
    
    -   You take a string and multiply it by an integer.
    -   The result is a new string containing the original string repeated the specified number of times.
-   **Example:**
    
    -   `"abc" * 3` results in `"abcabcabc"`.
    -   `"Python! " * 2` results in `"Python! Python! "`.
-   **Key Points:**
    
    -   The `*` operator requires an integer as the multiplier.
    -   Multiplying a string by zero results in an empty string.
    -   This is a very efficient way to create a longer string when you need repeating patterns.
-   **Use Cases:**
    
    -   Creating visual separators (e.g., `"-" * 20`).
    -   Generating repetitive patterns for text-based displays.
    -   Quickly building strings with repeated elements.

---
"""

# String repetition examples

base_string = "Hello"
repetition_count = 3

repeated_string = base_string * repetition_count

print(f"Original string: {base_string}")
print(f"Repeated string: {repeated_string}")

# Using repetition for visual separators
separator = "-" * 30
print(separator)

# Repeating with different strings and counts
pattern = "* "
repeated_pattern = pattern * 5
print(repeated_pattern)

# Repeating zero times
empty_string = "Test" * 0
print(f"Empty string: '{empty_string}'")

#using string repetition in a loop.
for i in range(1,6):
  print("*"*i)

"""## **Explanation:**

1.  **Basic Repetition:**
    -   We define a `base_string` and a `repetition_count`.
    -   The `*` operator multiplies the string by the count, creating `repeated_string`.
    -   f-strings are used to print the results.
2.  **Visual Separators:**
    -   We create a separator line using `"-" * 30`.
3.  **Different Patterns:**
    -   We demostrate creating a different repeating pattern.
4.  **Zero Repetition:**
    -   Demonstrates that multiplying by zero results in an empty string.
5.  **Loop Example**
    -   A for loop is used to print an increasing number of asterisks on each line, creating a triangle like pattern.

### **Comparison Operators for Strings in Python**

In Python, comparison operators work with **strings** based on **lexicographical order** (dictionary order), which follows the **Unicode values** of characters.

### **Examples of String Comparisons**
"""

# Define two strings
str1 = "apple"
str2 = "banana"

print("str1 == str2 = ",str1 == str2)  # False (because "apple" is not equal to "banana")
print("str1 != str2 = ",str1 != str2)  # True  (because "apple" is different from "banana")
print("str1 > str2  = ", str1 > str2)   # False (because "apple" comes before "banana" in dictionary order)
print("str1 < str2  = ", str1 < str2)   # True  (because "apple" comes before "banana")

"""
### **How String Comparison Works?**

-   **Python compares strings character by character** using their **Unicode values**.
    
-   `'a' < 'b'` because the Unicode value of `'a'` (97) is smaller than that of `'b'` (98).
    
-   `'apple' < 'banana'` → `'a' < 'b'`, so Python stops there.
    

### **Comparing Strings with Different Cases**"""

print('"Apple" > "apple"   = ', "Apple" > "apple")  # False ('A' has a smaller Unicode value than 'a')
print('"apple" == "APPLE") = ', "apple" == "APPLE") # False (case-sensitive)
print('"abc" < "abd"       = ', "abc" < "abd")      # True ('c' < 'd')

"""## **Using Comparison Operators in an If Statement**"""

word = "mango"

if word > "apple":
    print(f"{word} comes after apple in alphabetical order")
else:
    print(f"{word} comes before apple in alphabetical order")

"""#**Comprehensive Guide to Type Casting in Python** 🚀

## **What is Type Casting?**

Type casting (or type conversion) is the process of converting one data type into another. Python supports two types of type casting:

- **`Implicit`** Type Casting – Done `automatically` by Python.
- **`Explicit`** Type Casting – Done `manually using built-in functions`.

##1️⃣ **Implicit Type Casting (Automatic Conversion)**

Python automatically converts one data type to another `when no data loss occurs.`

Example 1: Converting int to float (`Safe Conversion`)
"""

num_int: int = 10
num_float = num_int + 5.5  # int + float = float. skipped type hint to see what data type is assigned at runtime
print(num_float, type(num_float))

"""### **Example 2: Converting int to complex**

✅ Python automatically promotes int to complex, as complex numbers `cannot be downgraded`.
"""

num_int: int = 7
num_complex: complex = num_int + 3j  # int + complex → complex
print(num_complex, type(num_complex))

# num_int automatically promotes int to complex type
num_int = num_complex
print(num_int, type(num_int))

"""### **Example 3: No Implicit Conversion Between str and int**

❌ Error: Python does NOT implicitly convert str to int. We must convert explicitly.


"""

num_str = "100"
num_int = 5

print(num_str + num_int)  # ❌ TypeError

print(int(num_str) + num_int) # ✅  casting str to int, arthmitic operation perfomed
print(num_str + str(num_int)) # ✅  casting int to str, string concatenation performed

"""## **2️⃣ Explicit Type Casting (Manual Conversion)**

Python provides several built-in functions for type conversion:

<br>

| function   | type           |   |
|------------|----------------|---|
| int(x)     | Integer        |   |
| float(x)   | Float          |   |
| complex(x) | Complex number |   |
| str(x)     | String         |   |
| bool(x)    | Boolean        |   |
| list(x)    | List           |   |
| tuple(x)   | Tuple          |   |
| set(x)     | Set            |   |
| dict(x)    | Dictionary     |   |
|            |                |   |

### **Integer Conversion (int())**

Used to convert float, string (`if valid number`), and boolean values to integers.

✅ Example 1: Float → Integer (`Removes Decimal Part`)


🔹 Note: int() `truncates` (removes) the decimal part, it does not round.
"""

num_float: float = 9.8
num_int = int(num_float) # skipped type hint to see what data type is assigned at runtime
print(num_int, type(num_int))

b: bool = True
print("int(b) = ", int(b))

"""✅ Example 2: String → Integer (Only Valid Numbers)

❌ Invalid Case: "123abc" cannot be converted to int(). It will raise a ValueError.
"""

num_str: str = "123"
#num_str = "123abc" #uncomment to see error

num_int = int(num_str) # skipped type hint to see what data type is assigned at runtime
print(num_int, type(num_int))

"""✅ Example 3: Boolean → Integer"""

print(int(True))   # Output: 1
print(int(False))  # Output: 0

"""## **Float Conversion (float())**

Converts integers, strings, and booleans to floating-point numbers.

✅ Example 1: Integer → Float
"""

num_int: int = 5
num_float = float(num_int) # skipped type hint to see what data type is assigned at runtime
print(num_float, type(num_float))

"""✅ Example 2: String → Float"""

num_str: str = "3.14"
num_float = float(num_str) # skipped type hint to see what data type is assigned at runtime
print(num_float, type(num_float))

"""## **String Conversion (str())**

Converts numbers, lists, tuples, dictionaries, and booleans to strings.

✅ Example 1: Number → String
"""

num: int = 100
num_str = str(num) # skipped type hint to see what data type is assigned at runtime
print(num_str, type(num_str))

"""✅ Example 2: Boolean → String"""

print(str(True))   # Output: "True"
print(str(False))  # Output: "False"

"""## **Boolean Conversion (bool())**

Converts other data types to boolean (True or False).

✅ Example:
"""

print("bool(1)       = ", bool(1))       # True
print("bool(0)       = ", bool(0))       # False
print("bool(-10)     = ", bool(-10))     # True (Non-zero numbers are True)
print('bool("")      = ', bool(""))      # False (Empty string)
print('bool("Hello") = ', bool("Hello")) # True (Non-empty string)
print("bool([])      = ", bool([]))      # False (Empty list)
print("bool([1, 2])  = ", bool([1, 2]))  # True (Non-empty list)

"""## **List, Tuple & Set Conversions**

Python allows converting between lists, tuples, and sets.

✅ Example 1: Tuple → List
"""

tup: tuple = (1, 2.7, 3, 'OB')
lst = list(tup) # skipped type hint to see what data type is assigned at runtime
print(lst, type(lst))

"""✅ Example 3: List → Set (Removes Duplicates)"""

lst: list = [1, 2, 2, 3, 4, 4, 5, "Agentic AI"]
s = set(lst)      # skipped type hint to see what data type is assigned at runtime
print(s, type(s))

"""## **Dictionary Conversion (dict())**

You can convert lists of key-value pairs into a dictionary.

✅ Example: List of Tuples → Dictionary
"""

lst: list = [("name", "Alice"), ("age", 25)]
d = dict(lst)       # skipped type hint to see what data type is assigned at runtime
print(d, type(d))

"""## **Complex Number Conversion (complex())**

Used to convert numbers into complex numbers (a + bj).

✅ Example:
"""

num: int = 5
comp = complex(num)   # skipped type hint to see what data type is assigned at runtime
print(comp, type(comp))  # Output: (5+0j) <class 'complex'>

num = str(comp)     # skipped type hint to see what data type is assigned at runtime
num

# TypeError: int() argument must be a string, a bytes-like object or a real number, not 'complex'
num = int(comp)
num

"""## **Conclusion**

✅ Implicit Conversion (Automatic, No Data Loss)

✅ Explicit Conversion (int(), float(), str(), etc.) for manual control

✅ Be careful when converting strings (avoid invalid format errors)
"""