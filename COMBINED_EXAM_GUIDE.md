# PYTHON PROGRAMMING - COMBINED EXAM REVISION GUIDE
## 1BPLC105B/205B | Time: 3 Hours | Max Marks: 100

**Instructions:** Answer any FIVE full questions, choosing at least ONE from each MODULE

---

## MODULE - 1: Python Basics & Control Flow

### **SECTION A: Theory Questions (4-5 Marks)**

#### Q1.a: Type Conversion in Python
**Question:** Explain type conversion. Differentiate between implicit and explicit conversion with examples.

**Answer (4-5 marks):**
- **Type Conversion:** Converting one data type to another
- **Implicit Conversion:** Python automatically converts (no code needed)
  - Example: `x = 5 + 2.5` → x becomes 7.5 (int + float = float)
- **Explicit Conversion:** Programmer explicitly converts using functions
  - `int()`, `float()`, `str()`, `bool()`
  - Example: `str(123)` → "123", `int("45")` → 45
- **Key difference:** Implicit is automatic; explicit requires function calls
- **Implicit risk:** Can lose data (float to int), explicit gives control

#### Q1.c: Syntax Error vs Runtime Error
**Question:** Differentiate between syntax error and runtime error with examples.

**Answer (4 marks):**
- **Syntax Error:**
  - Caught before program runs (during parsing)
  - Example: `if x = 5:` (missing colon), `print("hello` (unclosed quote)
  - Program won't execute at all
- **Runtime Error:**
  - Occurs during program execution
  - Example: `1/0` (ZeroDivisionError), `int("abc")` (ValueError)
  - Program starts but crashes during execution

#### Q2.c: Function Composition
**Question:** What is function composition? Illustrate with an example.

**Answer (4 marks):**
- **Definition:** Combining two or more functions where output of one becomes input of another
- **Syntax:** `result = f(g(x))`
- **Example:**
  ```python
  def add_five(x):
      return x + 5
  def multiply_two(x):
      return x * 2
  
  result = add_five(multiply_two(3))  # 3*2 = 6, 6+5 = 11
  ```
- **Benefits:** Code reusability, cleaner logic

---

### **SECTION B: Programming Questions (8 Marks)**

#### Q1.b: Fibonacci Sequence
**Question:** Develop a program with while loop to display Fibonacci sequence up to n terms.

**Answer (8 marks):**
```python
n = int(input("Enter number of terms: "))
a, b = 0, 1
count = 0
print(f"Fibonacci sequence up to {n} terms:")
while count < n:
    print(a, end=" ")
    a, b = b, a + b
    count += 1
```

#### Q2.b: Numbers Divisible by 3 or 5 (but not both)
**Question:** Print numbers 1-100 divisible by 3 or 5 but NOT both using continue/break.

**Answer (8 marks):**
```python
print("Numbers divisible by 3 or 5 but not both:")
for i in range(1, 101):
    if (i % 3 == 0 and i % 5 == 0):
        continue  # Skip if divisible by both
    if (i % 3 == 0 or i % 5 == 0):
        print(i, end=" ")
```

#### Q2.a: Collatz Sequence
**Question:** Describe Collatz 3n+1 sequence and explain iteration/conditional statements in implementation.

**Answer (8 marks):**
```python
# Collatz Sequence: If n is even → n/2, if odd → 3n+1, repeat until n=1
n = int(input("Enter number: "))
print(f"Collatz sequence for {n}:")
while n != 1:
    print(n, end=" → ")
    if n % 2 == 0:
        n = n // 2
    else:
        n = 3 * n + 1
print(1)

# Iteration (while loop) repeats until n becomes 1
# Conditional (if-else) determines operation based on even/odd
```

---

## MODULE - 2: Strings, Lists & Data Structures

### **SECTION A: Theory Questions (4-5 Marks)**

#### Q3.a: String Operations
**Question:** Explain string operations - slicing, concatenation, repetition, comparison with examples.

**Answer (4-5 marks):**
- **Slicing:** Extracting substring using `string[start:end]`
  - Example: `"Python"[0:3]` → "Pyt"
- **Concatenation:** Joining strings with `+`
  - Example: `"Hello" + " " + "World"` → "Hello World"
- **Repetition:** Repeating strings with `*`
  - Example: `"Hi" * 3` → "HiHiHi"
- **Comparison:** Using `==`, `<`, `>` operators
  - Example: `"abc" < "def"` → True (alphabetical order)

#### Q3.b: List vs Array
**Question:** Define list. How is it different from array? Access third element of [3, 6, 9, 12].

**Answer (4 marks):**
- **List:** Ordered collection of items (any data type) in Python
- **Differences from Array:**
  - Lists are dynamic (size changes), arrays have fixed size
  - Lists can have mixed types, arrays typically same type
  - Lists built-in Python, arrays from NumPy library
- **Accessing third element:** `nums = [3, 6, 9, 12]; print(nums[2])` → Output: 9

#### Q4.a: Mutability in Lists
**Question:** Explain mutability in lists. Difference between modifying and cloning with examples.

**Answer (4-5 marks):**
- **Mutability:** Lists can be changed after creation (mutable)
- **Modifying list:**
  ```python
  x = [1, 2, 3]
  x[0] = 99  # Changes original list to [99, 2, 3]
  y = x      # y points to same object, both change together
  ```
- **Cloning list:**
  ```python
  x = [1, 2, 3]
  y = x.copy()  # or y = x[:] - creates new separate list
  y[0] = 99     # Only y changes, x remains [1, 2, 3]
  ```

---

### **SECTION B: Programming Questions (6-8 Marks)**

#### Q3.c: Count Words in Text
**Question:** Develop program to count number of words in given line of text.

**Answer (6 marks):**
```python
text = input("Enter a line of text: ")
words = text.split()
word_count = len(words)
print(f"Number of words: {word_count}")

# Alternative with word frequency:
word_freq = {}
for word in words:
    word_freq[word] = word_freq.get(word, 0) + 1
print(f"Word frequency: {word_freq}")
```

#### Q4.b: Palindrome Check Using Slicing
**Question:** Develop program to check if string is palindrome using slicing.

**Answer (6 marks):**
```python
string = input("Enter a string: ")
# Remove spaces and convert to lowercase
clean = string.replace(" ", "").lower()

# Check if string equals its reverse
if clean == clean[::-1]:
    print(f"'{string}' is a palindrome")
else:
    print(f"'{string}' is not a palindrome")

# Explanation: [::-1] reverses string using slicing
```

#### Q4.c: Filter Even Numbers
**Question:** Program that takes list of numbers and returns new list with only even numbers.

**Answer (6 marks):**
```python
numbers = [int(x) for x in input("Enter numbers (space-separated): ").split()]

# Method 1: Using loop
even_numbers = []
for num in numbers:
    if num % 2 == 0:
        even_numbers.append(num)

# Method 2: Using list comprehension (cleaner)
even_numbers = [num for num in numbers if num % 2 == 0]

print(f"Even numbers: {even_numbers}")
```

---

## MODULE - 3: Dictionaries, NumPy & File Handling

### **SECTION A: Theory Questions (4-5 Marks)**

#### Q5.c: 'with' Statement in File Handling
**Question:** Explain the use of 'with' statement in file handling with a program.

**Answer (4 marks):**
- **Purpose:** Automatically manages file opening and closing
- **Advantages:**
  - No need for explicit `close()` call
  - Ensures file closes even if error occurs
  - Cleaner, safer code
- **Example:**
  ```python
  with open("file.txt", "r") as f:
      data = f.read()
  # File automatically closes here, no .close() needed
  ```

#### Q5.a: Dictionary Features & Operations
**Question:** Explain key features of Python dictionaries. How different from lists? Illustrate insertion, deletion, lookup.

**Answer (4-5 marks):**
- **Features:** Key-value pairs, unordered (Python 3.7+ ordered), mutable
- **Difference from lists:**
  - Lists: indexed by position [0,1,2...], dictionaries by key
  - Dictionaries: unordered access, lists: ordered
- **Operations:**
  ```python
  student = {"name": "John", "age": 20}  # Creation
  student["marks"] = 85  # Insertion
  del student["age"]     # Deletion
  print(student["name"]) # Lookup
  ```

#### Q5.b: NumPy Masking
**Question:** What is masking in NumPy? Develop program to illustrate masking to filter array elements.

**Answer (4-6 marks):**
- **Masking:** Creating boolean array to filter elements meeting condition
- **Example:**
  ```python
  import numpy as np
  arr = np.array([1, 2, 3, 4, 5, 6])
  mask = arr > 3           # Boolean mask: [F,F,F,T,T,T]
  filtered = arr[mask]     # Result: [4, 5, 6]
  ```

#### Q6.c: Binary vs Text Files
**Question:** Explain how binary files differ from text files. Illustrate with suitable program segments.

**Answer (4 marks):**
- **Text Files:**
  - Contain human-readable characters
  - Open mode: `"r"`, `"w"`
  - Platform-specific line endings
- **Binary Files:**
  - Contain raw bytes (images, audio, executables)
  - Open mode: `"rb"`, `"wb"`
  - No line-ending conversion
- **Example:**
  ```python
  # Text file
  with open("file.txt", "r") as f:
      text = f.read()
  
  # Binary file
  with open("image.png", "rb") as f:
      binary_data = f.read()
  ```

---

### **SECTION B: Programming Questions (8 Marks)**

#### Q5.a: Word Frequency Counter
**Question:** Develop program to count word frequency in paragraph using dictionary and display top 3 words.

**Answer (8 marks):**
```python
paragraph = input("Enter paragraph: ")
words = paragraph.lower().replace(".", "").replace(",", "").split()

# Count frequency
word_freq = {}
for word in words:
    word_freq[word] = word_freq.get(word, 0) + 1

# Sort by frequency and get top 3
top_3 = sorted(word_freq.items(), key=lambda x: x[1], reverse=True)[:3]

print("Top 3 most frequent words:")
for word, count in top_3:
    print(f"{word}: {count}")
```

#### Q5.b: NumPy Masking Program
**Question:** Develop NumPy program to illustrate masking to filter array elements.

**Answer (6-8 marks):**
```python
import numpy as np

arr = np.array([10, 25, 5, 30, 15, 8, 40])
print(f"Original array: {arr}")

# Mask: elements > 15
mask = arr > 15
filtered = arr[mask]
print(f"Elements > 15: {filtered}")

# Mask: even numbers
even_mask = arr % 2 == 0
print(f"Even numbers: {arr[even_mask]}")

# Conditional filtering
result = arr[(arr > 10) & (arr < 35)]
print(f"Between 10 and 35: {result}")
```

#### Q6.b: NumPy Matrix Operations
**Question:** Develop NumPy program: Create 3×3 matrix, display shape, transpose, mean.

**Answer (6 marks):**
```python
import numpy as np

# Create 3x3 random matrix
matrix = np.random.randint(1, 100, (3, 3))
print("Matrix:\n", matrix)

# Shape
print(f"Shape: {matrix.shape}")

# Transpose
print("Transpose:\n", matrix.T)

# Mean of all elements
print(f"Mean: {matrix.mean()}")
```

---

## MODULE - 4: Modules, Namespaces & Object-Oriented Basics

### **SECTION A: Theory Questions (4-5 Marks)**

#### Q7.c: Class Attribute vs Instance Attribute
**Question:** Differentiate between class attribute and instance attribute with suitable program segments.

**Answer (4 marks):**
- **Class Attribute:** Shared by all instances, defined inside class but outside methods
  ```python
  class Student:
      college = "XYZ College"  # Class attribute
      def __init__(self, name):
          self.name = name     # Instance attribute
  ```
- **Instance Attribute:** Unique to each object, defined in `__init__`
- **Difference:**
  - Class: shared memory, accessed via `Class.attribute` or `obj.attribute`
  - Instance: individual memory, accessed via `obj.attribute`
  - Changing class attribute affects all instances; changing instance affects only that object

#### Q8.c: 'is' vs '==' Operators
**Question:** Explain difference between 'is' and '==' using immutable objects.

**Answer (4 marks):**
- **`==`:** Compares VALUES (content)
- **`is`:** Compares IDENTITY (memory location)
- **Example with immutable objects:**
  ```python
  a = 5
  b = 5
  print(a == b)      # True (same value)
  print(a is b)      # True (same object - Python caches small integers)
  
  x = "hello"
  y = "hello"
  print(x == y)      # True (same value)
  print(x is y)      # True (string interning in Python)
  
  c = [1, 2]
  d = [1, 2]
  print(c == d)      # True (same content)
  print(c is d)      # False (different objects)
  ```

#### Q7.a: Random & Time Modules
**Question:** Explain use of random and time modules in Python. Develop program simulating stopwatch.

**Answer (4-8 marks):**
```python
import random
import time

# Random module: generates random numbers
# time module: works with time delays and timing

print("Simple Stopwatch Simulator:")
num_intervals = 3
times = []

for i in range(num_intervals):
    interval = random.uniform(1, 5)  # Random delay 1-5 seconds
    times.append(interval)
    print(f"Interval {i+1}: {interval:.2f} seconds")
    time.sleep(interval)

avg_time = sum(times) / len(times)
print(f"Average time: {avg_time:.2f} seconds")
```

#### Q7.b: Namespaces & LEGB Rule
**Question:** Explain namespaces in Python. Develop program illustrating LEGB rule.

**Answer (4-8 marks):**
```python
# LEGB: Local, Enclosing, Global, Built-in

x = "Global"  # Global scope

def outer():
    x = "Enclosing"  # Enclosing scope
    
    def inner():
        x = "Local"  # Local scope
        print(x)     # Finds 'Local' first (L)
    
    inner()
    print(x)         # Finds 'Enclosing' (E)

outer()
print(x)             # Finds 'Global' (G)

# Python searches: Local → Enclosing → Global → Built-in
```

---

### **SECTION B: Programming Questions (8 Marks)**

#### Q8.a: Custom Module Creation
**Question:** Create utilities.py with functions for square, cube, factorial. Import in another file using all 3 variants.

**Answer (8 marks):**

**File 1: utilities.py**
```python
def square(n):
    return n ** 2

def cube(n):
    return n ** 3

def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)
```

**File 2: main.py**
```python
# Import variant 1: Import entire module
import utilities
print(utilities.square(5))      # 25
print(utilities.cube(3))        # 27

# Import variant 2: Import specific functions
from utilities import square, cube
print(square(4))                # 16
print(cube(2))                  # 8

# Import variant 3: Import all with alias
from utilities import *
print(factorial(5))             # 120
```

#### Q8.b: Custom Module for Binomial Coefficient
**Question:** Develop custom module with factorial function. Import to calculate binomial coefficient.

**Answer (8 marks):**

**File 1: math_operations.py**
```python
def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)
```

**File 2: binomial.py**
```python
from math_operations import factorial

def binomial_coefficient(n, r):
    """Calculate C(n,r) = n! / (r! * (n-r)!)"""
    if r > n:
        return 0
    return factorial(n) // (factorial(r) * factorial(n - r))

n = int(input("Enter n: "))
r = int(input("Enter r: "))
result = binomial_coefficient(n, r)
print(f"C({n},{r}) = {result}")
```

---

## MODULE - 5: Object-Oriented Programming & Exception Handling

### **SECTION A: Theory Questions (4-5 Marks)**

#### Q9.c: Operator Overloading
**Question:** What is operator overloading? Illustrate with example using `__add__()`.

**Answer (4 marks):**
- **Definition:** Redefining operators (+, -, *, etc.) to work with custom objects
- **Method:** Use special methods like `__add__()`, `__sub__()`, etc.
- **Example:**
  ```python
  class Point:
      def __init__(self, x, y):
          self.x = x
          self.y = y
      
      def __add__(self, other):
          return Point(self.x + other.x, self.y + other.y)
      
      def __str__(self):
          return f"({self.x}, {self.y})"
  
  p1 = Point(1, 2)
  p2 = Point(3, 4)
  p3 = p1 + p2  # Calls __add__()
  print(p3)      # (4, 6)
  ```

#### Q10.c: Finally Clause Role
**Question:** Explain role of finally clause with example.

**Answer (4 marks):**
- **Purpose:** Execute code regardless of whether exception occurs
- **Usage:** Always executes after try/except blocks
- **Common use:** Clean up resources (close files, release connections)
- **Example:**
  ```python
  try:
      file = open("file.txt", "r")
      data = file.read()
  except FileNotFoundError:
      print("File not found")
  finally:
      file.close()  # Always executes
  ```

---

### **SECTION B: Programming Questions (8 Marks)**

#### Q9.a: Point Class & Mutability
**Question:** Create Point class with attributes x, y. Demonstrate sameness using 'is', show effect of mutability.

**Answer (8 marks):**
```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __str__(self):
        return f"Point({self.x}, {self.y})"

# Create points
p1 = Point(3, 4)
p2 = p1
p3 = Point(3, 4)

# Sameness test with 'is'
print(p1 is p2)        # True (same object)
print(p1 is p3)        # False (different objects)
print(p1 == p3)        # False (no __eq__ defined)

# Mutability effect
print(f"Before: p1={p1}, p2={p2}")
p1.x = 5
print(f"After: p1={p1}, p2={p2}")  # p2 also changed (same reference)

# p3 not affected
print(f"p3={p3}")                    # Still (3, 4)
```

#### Q9.b: Exception Handling
**Question:** Explain need for exception handling. Develop program illustrating try, except, else, finally.

**Answer (8 marks):**
```python
# Exception handling prevents program crash and allows graceful error handling

try:
    num1 = int(input("Enter dividend: "))
    num2 = int(input("Enter divisor: "))
    result = num1 / num2
    
except ZeroDivisionError:
    print("Error: Cannot divide by zero")
    
except ValueError:
    print("Error: Enter valid integers")
    
else:
    # Executes if NO exception in try
    print(f"Division result: {result}")
    
finally:
    # Always executes
    print("Division operation completed")

# Flow:
# - try: Execute code
# - except: Handle if error occurs
# - else: Run if NO error
# - finally: Always run (cleanup)
```

#### Q10.a: Polymorphism
**Question:** Develop program to illustrate polymorphism by defining common interface method in two classes.

**Answer (8 marks):**
```python
# Polymorphism: Different classes with same method name behave differently

class Animal:
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Woof! Woof!"

class Cat(Animal):
    def sound(self):
        return "Meow! Meow!"

class Cow(Animal):
    def sound(self):
        return "Moo! Moo!"

# Using polymorphism
animals = [Dog(), Cat(), Cow()]

for animal in animals:
    print(animal.sound())  # Same method, different output

# Output:
# Woof! Woof!
# Meow! Meow!
# Moo! Moo!
```

#### Q10.b: Pure Functions vs Modifiers
**Question:** Outline difference between pure functions and modifiers. Develop BankAccount class example.

**Answer (8 marks):**
```python
class BankAccount:
    def __init__(self, balance):
        self.balance = balance
    
    # Pure Function: Returns new value, doesn't modify original
    def calculate_interest(self, rate):
        return self.balance * (1 + rate / 100)
    
    # Modifier Function: Changes object state
    def deposit(self, amount):
        self.balance += amount
        return self.balance
    
    # Modifier Function: Changes object state
    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            return self.balance
        return "Insufficient funds"

# Usage
account = BankAccount(1000)
print(f"Balance: {account.balance}")           # 1000

# Pure function (doesn't change balance)
interest = account.calculate_interest(5)       # 1050
print(f"With 5% interest: {interest}")
print(f"Actual balance: {account.balance}")     # Still 1000

# Modifier functions (change balance)
account.deposit(500)                           # 1500
print(f"After deposit: {account.balance}")     # 1500

account.withdraw(200)                          # 1300
print(f"After withdrawal: {account.balance}")  # 1300
```

---

## QUICK REFERENCE - KEY CONCEPTS

### Important Functions to Remember
| Concept | Code |
|---------|------|
| Fibonacci | `a, b = 0, 1` then `a, b = b, a+b` |
| Reverse String | `string[::-1]` |
| List to String | `" ".join(list)` |
| Split String | `string.split()` |
| Dictionary Sort | `sorted(dict.items(), key=lambda x: x[1])` |
| List Comprehension | `[x for x in list if condition]` |
| File Handling | `with open(file) as f:` |
| Random Number | `random.randint(a, b)` or `random.uniform(a, b)` |

### Common Error Types
- **SyntaxError:** Missing colon, quotes, brackets
- **ValueError:** Wrong data type conversion
- **ZeroDivisionError:** Division by zero
- **KeyError:** Accessing non-existent dict key
- **IndexError:** Accessing out-of-range list index
- **FileNotFoundError:** File doesn't exist

---

## TIPS FOR EXAM

✅ **For 4-5 Mark Answers:**
- Define the concept (1 mark)
- Explain key points (2-3 marks)
- Provide examples/code (1-2 marks)

✅ **For 8-10 Mark Answers:**
- Problem explanation (1 mark)
- Full code with comments (6-8 marks)
- Output example (1 mark)

✅ **General Tips:**
- Write code clearly with proper indentation
- Use meaningful variable names
- Add comments explaining logic
- Test logic mentally before writing
- Allocate time: 5 min per question planning, 15 min for solving

---

**Good luck for your exam on Monday! 🎓**
