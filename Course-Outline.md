# Coding with Python - Syllabus - MC 2018

Every class will introduce some basic concepts in Python, and give students opportunities to code and play around with the concepts. Every class will have a couple of goal projects that show off the topics learned in that class.

The syllabus is meant to complement the (free) Codecademy Python course. Students can use that course to reinforce and practice outside of class time. It contains other exercises and projects that students may wish to attempt. This class will be specialized towards using Python as a mathematician would use it.

https://www.codecademy.com/courses/learn-python

Many of the projects are taken from Project Euler, a collection of math programming challenges.

https://projecteuler.net/archives

## Week 1 - The basics

### 1-1. Python Syntax 

1. Basic `print`ing. (`"Hello World!"`, `'` vs `"`, Python 2 vs Python 3)
2. Variables (`=`)
3. Arithmetic (data type, `+`, `-`, `*`, `/`, `%`, powers)
4. Updating variables (`+=`, `*=`)
5. Comments (`#`, `"""Docstrings"""`)
6. Numbers (`Int`, `Float`, 1/3, division)
7. Booleans (`True`, `False` using `1` or `0`)
8. Changing data types (`int()`, `float()`, `str()`, `type()`)

Project: Largest number with small number of characters, Project Euler Problem 6.

### 1-2. Strings and Printing

1. Escaping characters
2. Index and Truncating
3. String methods (`.upper()`, `.lower()`, `.split()`, `len()`, `.replace()`, `.find()`)
4. Basic string concatination (`+`)
5. String replacement formatting (`%`)
6. Input from the user (`input()`, `raw_input()`)

Project: Madlibs.

### 1-3. Conditionals and Control Flow

1. Comparisons, (`==`, `!=`, `<`, `>`, `<=`, `>=`)
2. Logical operators(`and`, `or`, `not`) 
3. Conditionals (`If`/`else`, `elif`, indents, formatting)
4. How Python treats non-Booleans

Project: Project Euler 1 (part 1), Pig Latin translator.

## Week 2 - Functions, lists and loops!

This week we gain the tools to start doing powerful things. Loops will allow us to get `Python` to make tedious, repetitive calculations. What will we ask `Python` to do?

### 2-1. Functions, Import, Random, math.

1. Structure/purpose of functions (`def`, docstring, body, `return`)
2. Arguments, parameters (scope)
3. Built-in functions (`min()`, `max()`, `abs()`, `len()`)
4. Iterators
5. Import (`from`/`import`, `random`, `math`)
6. Math module (`sqrt`, `factorial`, `e`, `log`)
7. Random module (`.randint(a, b)`, `.random()`, `.uniform(a,b)`, `.seed()`)
8. Other modules. (`dir()`, `datetime`, `time`, `itertools`)

Project: Compute e randomly by trials.

### 2-2. Lists

1. What can go in lists? (strings, integers, lists)
2. `append()`, `remove()`
3. List methods (`len()`, `max()`, `min()`, `sum()`, `sorted()`, `reverse()`)
4. List splicing and indexing
5. `range(n)`
6. Your first `for` loop
7. `enumerate`, tuples
8. `zip`

Project: Project Euler 1 (part 2), Project Euler Problem 16

### 2-3. Loops (`for`, `while`)

1. `range(n)` review
2. `for` loop (index, formatting, indent)
3. Looping over strings.
4. Combining `for` and `if`
5. `break`
6. `for`/`else`
7. nested loops (order, good naming, runtime)
8. `while` loop (formatting, indent, infinite loops)
9. `break`
10. `while`/`else` (formatting, when is the else executed)

Project: Make a number guessing game, produce Fibonacci numbers, Prime sieve

### 2-4.  Lists, Dictionaries and Sets

1. List comprehesion 1. (using `for`)
2. List comprehension 2. (using `if`)
3. Dictionaries: Keys and values
4. Defining dictionaries explicitly, by value, by comprehension
5. Dictionary Methods (`.keys()`, `.values()`, sorting)
6. Sets: (Defininition, what they are used for, unordered)
7. What can go in a set?
8. Getting the number of unique elements of a list.

Project: Project Euler Problem 20, Prime Factor decomposition

## Week 3 - Advanced basics

This week will be less dense in content to give students a chance to catch up and complete projects.

### 3-1. Computational thinking and practical concerns

1. Making a plan. (Test cases, `pass`)
2. Brute force algorithms.
3. Runtime and memory differences (for loops, comprehension, lists vs iterators)
4. Debug tools (printing, `assert`)
5. Python 2 vs Python 3, continued.

Project: Project Euler Problems 81, 82, 83 (part 1)

### 3-2. File input/Output

1. Reading files. (open, close, '\n')
2. Writing to files. (`w`, `w+`)

Project: Project Euler Problem 13, Project Euler Problems 81, 82, 83 (part 2)

### 3-3. Numpy, stats and vectors

1. `import`/`as`.
2. Numpy arrays vs lists
3. Statistical methods (mean, median, mode, standard deviation, variance)
4. Linear regression (using the scipy package)

Project: Interpolating real data

### 3-4. APIs

1. What is an API? What types are there? (e.g. NASA, ISS, MARTA, Twitter, Youtube)
2. What does the data look like? (json)
3. API keys (rate limits)
4. Making requests

Project: Making a heatmap of Atlanta's bus system
