# PYTHON PROGRAMMING - COMBINED EXAM REVISION GUIDE
## 1BPLC105B/205B | Time: 3 Hours | Max Marks: 100

## MODULE - 4: File Handling, Debugging & OOP Basics

### **SECTION A: Q7**

#### Q7.a: os.walk()
**Question:** Demonstrate the working of os.walk() with example.

**Answer (10 marks):**
- **os.walk()** traverses a directory tree top to bottom.
- It returns a tuple of **current directory**, **subdirectories**, and **files**.
- It is useful for searching files and processing folders recursively.
```python
import os
## MODULE - 4: File Handling, Debugging & OOP Basics

### **SECTION A: Q7**

#### Q7.a: os.walk()
**Question:** Demonstrate the working of os.walk() with example.

**Answer (10 marks):**
- **os.walk()** traverses a directory tree top to bottom.
- It returns a tuple of **current directory**, **subdirectories**, and **files**.
- It is useful for searching files and processing folders recursively.
```python
import os

root_dir = "."

for current_path, subdirs, files in os.walk(root_dir):
    print("Current Path:", current_path)
    print("Subdirectories:", subdirs)
    print("Files:", files)
    print("-" * 40)
```

#### Q7.b: Assertions and Compressing Files
**Question:** Describe the following: i) Assertions ii) Compressing files.

**Answer (10 marks):**
- **Assertions:** Used to test if a condition is true while debugging.
- If the condition becomes false, Python raises an **AssertionError**.
- **Compressing files:** Combines one or more files into a compressed archive, usually using the `zipfile` module.
```python
# Assertions
age = 18
assert age >= 18, "Age must be 18 or above"

# Compressing files
import zipfile

with zipfile.ZipFile("archive.zip", "w", zipfile.ZIP_DEFLATED) as zipf:
    zipf.write("file1.txt")
    zipf.write("file2.txt")

print("Files compressed successfully")
```

---

## MODULE - 5: Object-Oriented Programming

### **SECTION A: Q9**

#### Q9.a: __init__() and __str__()
**Question:** Interpret the significance of __init__() and __str__() method with example.

**Answer (10 marks):**
- **__init__()** is the constructor method that initializes object data when an object is created.
- **__str__()** returns a readable string representation of the object.
- These methods make classes easier to use and print.
```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def __str__(self):
        return f"Student Name: {self.name}, Marks: {self.marks}"

s = Student("John", 85)
print(s)
```

#### Q9.b: Rectangle Using OOP
**Question:** Develop a program for constructing the rectangle using the concept of object oriented programming.

**Answer (10 marks):**
```python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * (self.length + self.width)

    def display(self):
        print(f"Rectangle: {self.length} x {self.width}")
        print(f"Area: {self.area()}")
        print(f"Perimeter: {self.perimeter()}")

rect = Rectangle(10, 5)
rect.display()
```

---

### **OR**

#### Q10.a: Operator Overloading
**Question:** Explain any polymorphism of operator overloading used in OOP.

**Answer (10 marks):**
- Operator overloading means giving a built-in operator a new meaning for user-defined objects.
- It is a form of polymorphism because the same operator behaves differently for different object types.
- Special methods such as `__add__()` are used for this purpose.
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
p3 = p1 + p2
print(p3)
```

#### Q10.b: Student Marks Program
**Question:** Develop a program that uses class student which prompts the user to enter marks in three subjects and calculate total marks and percentage.

**Answer (10 marks):**
```python
class Student:
    def __init__(self, name):
        self.name = name
        self.marks = []

    def input_marks(self):
        for i in range(3):
            mark = float(input(f"Enter marks in subject {i + 1}: "))
            self.marks.append(mark)

    def total_marks(self):
        return sum(self.marks)

    def percentage(self):
        return (self.total_marks() / 300) * 100

    def display_result(self):
        print(f"\nStudent: {self.name}")
        print(f"Total Marks: {self.total_marks()}")
        print(f"Percentage: {self.percentage():.2f}%")

student = Student("Rishi")
student.input_marks()
student.display_result()
```
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
