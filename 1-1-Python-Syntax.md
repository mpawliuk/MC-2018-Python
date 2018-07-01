# 1-1 Python Syntax

Welcome to `Python` at Math Circle! In this course we will learn how to use the computer language `Python` to help us as mathematicians. Computers can be very helpful tools. Lots of modern mathematics uses computers to automate calculations, or search for counterexamples, or to visualize results.

You will also start to think "like a coder" as we progress through the lessons. You will analyze problems more carefully and approach solutions in a different way. Even if you don't end up using `Python` very much, this perspective will be very helpful.

A note about the sturcture: Learning to code is literally learning a new language. Each day we will focus on a couple of words in the language, and we will quickly learn how to make sentences and have conversations. Especially at the beginning you will forget a lot of the syntax and formatting; that's normal! Get used to searching through the [Python Documentation](https://docs.python.org/3/) which is surprisingly readable, and very helpful! For example, try Googling `Python 3 range` and find the appropriate section in the documentation that explains it. 

There are two common versions of `Python`: `Python 2` and `Python 3`. For the most part they work very similarly, however there are a couple important differences. We will be using `Python 3`. I'll discuss them later once we have more experience with coding.

These notes will contain only the basics, some code we mention in class, and the exercises.

## Outline

1. Basic `print`ing. (`"Hello World!"`, `'` vs `"`, Python 2 vs Python 3)
2. Variables (`=`)
3. Arithmetic (data type, `+`, `-`, `*`, `/`, `%`, powers)
4. Updating variables (`+=`, `*=`)
5. Comments (`#`, `"""Docstrings"""`)
6. Numbers (`Int`, `Float`, 1/3, division)
7. Booleans (`True`, `False` using `1` or `0`)
8. Changing data types (`int()`, `float()`, `str()`, `type()`)

Project: Largest number with small number of characters, Project Euler Problem 6.

## 1. Basic `print`ing.

To display something to the user we use `print()`.

```Python
print("Hello World!")
>>>> Hello World!
```

For printing words or sentences, you need to wrap it in either single quotation marks (`'like this'`) or double quotation marks (`"like this"`). Don't mix them! Numbers can be printed without quotation marks, or with if you really want!

```python
print("I am coding.")
>>>> I am coding.
print(145)
>>>> 145
print("1234")
>>>> 1234
```

You can `print` multiple things at once if you separate them by commas.

```python
print("Atlanta", "GA", 33.7490, "N", 84.3880, "W")
>>>> Atlanta GA 33.7490 N 84.3880 W
```

### Exercise

`Print` your **name**, **age** and **country** in one line.

## 2. Variables

You can store information in variables. Name the variable whatever you like, but try to keep them descriptive. Use lower case letters when possible. 

To set a variable, use `=`. Once a variable has been set, it can be called and used later.

```python
city = "Atlanta"
state = "GA"
population = 486290

print(city, population)
>>>> Atlanta 486290
```

Variables can be overwritten by setting them again later in the code.

```python
city = "Atlanta"
state = "GA"
population = 486290

print(city, state, population)
>>>> Atlanta GA 486290

city = "Calgary"
population = 1266000

print(city, state, population)
>>>> Calgary GA 1266000
```

Here we rewrote the `city` and `population` variables, but we did not change the `state` variable.

### Technical note

Naming a variable is called *declaring* the variable, and setting a variable is called *initializing* it.

One thing that makes `Python` easy to code in is that you do not need to tell it what sort of information will be stored in the variable when you declare it. It can be a number or a word or a list. Other languages make you specify the `type` of the information ahead of time. This means that `Python`

### Exercise

Reset the variables in this code to match your personalized information, and add an additional variable that has some info about your city. Then `print` it. If you have no state, then don't print it.

```python
city = "Atlanta"
state = "GA"
population = 486290

city = "My city name"
state = "My state name"
population = 

print()
```

## 3. Arithmetic

Python is good at arithmetic. The basic operations are:

Symbol|Name|Example | Output
---|---|---|---
`+`|add|`3+2`|`5`
`-`|subtract|`3-2`| `1`
`*`|multiply|`3*2`| `6`
`/`|divide|`3/2`| `1.5`
`**`|exponent|`3**2`| `9`

You can use brackets if you like, and you should if it makes the code more readable. You can also leave white space between the numbers and the operations if it helps the code be more readable.

```python
3*2 + 4*5
>>>> 26
```

The operation `a//b` returns the (integer) quotient of `a` divided by `b`, and `a%b` returns the (integer) remainder of `a` divided by `b`.

```python
7//3
>>>> 2
7%3
>>>> 1
(7//3)*3 + 7%3
>>>> 7
```

### Technical note

`Python` follows the order of operations in order from left to right, except for powers which are performed right to left.

1. `+x`, `-x`
2. `x ** y`
3. `x * y`, `x / y`, `x // y`, `x % y`
4. `x + y`, `x - y`

When it isn't clear use brackets!

```python
12/2*2
>>>> 4.0
12/(2*2)
>>>> 3.0
```

Powers are performed right to left.

```python
2**2**3
>>>> 256
2**(2**3)
>>>> 256
(2**2)**3
>>>> 64
```

### Exercise

Find a way to determine if a number `n` is even using only:

1. `n`,
2. the operations `//` and `%`, and
3. The digits `0, 1, 2, 3, ..., 9`.

In other words, give an expression (e.g. `2//n + n%4`) that is equal to `0` when `n` is even, and `1` when `n` is odd. Can you produce a similar expression for when a number is divisible by `13`?

## 4. Updating variables

You can update a variable in two ways.

```python
height = 20
height = height + 4

print(height)
>>>> 24
```

or you can use the operation `+=`,

```python
height = 20
height += 4

print(height)
>>>> 24
```
    
This also works for strings.

```python
name = "Mike"
name += "Andrew"
name += "Pawliuk"

print(name)
>>>> MikeAndrewPawliuk
```

You can also use `*=`, `-=`, `/=` and `//=`.

### Exercise

We want to keep track of when our schedule at MC. Starting a 9 AM, add time in hours for each section of the day. Then print out:

1. The time.
2. The time on the 12 hour clock. (Use `%`.)
3. The time on the 12 hour and whether it is AM or PM.

```python
time = 9

# Morning class
time += 0
# Morning elective
time += 0
# Lunch
time += 0
# Afternoon class
time += 0

print()
```

## 5. Comments

To include one-line comments, use `#`. Python will ignore these. This is useful for giving line-by-line explanations.

```python
x = 7
# x += 4
x += 1
print(x)
>>>> 8

y = 13
print(y // 5) # This is an integer
>>>> 2
print(y/5) # This is a decimal
>>>> 2.6
```

To include longer comments use triple quotations `"""like this"""`. This is used for longer explanations of code, usually at the beginning of the code. It can skip lines.

```python
""""We want the formula for the area of a triangle.
 -b, the base is an integer
 -h, the height is an integer
"""
b = 3
h = 10
area = b*h/2
print(area)
>>>> 15.0
```

### Exercise

This code contains an error. Don't worry about fixing the error; just comment out the line that is producing the error, then run the code.

```python
a = 8
b = 12
c = 0
d = 2

print(a+b)
print(c+d)
print(b/a)
print(a/c)
print(a+b+c+d)
```

### Exercise

Ursula has written some code for a geometry project that automotically computes areas and volumes of some common shapes. She has been very lazy though and has not commented anything. Add comments after each formula that explains what it is.

```python
x = 2
y = 3
pi = 3.14
r = 4

print(x*y) # Area of ...
print(x**2) # Area of ...
print(x*y/2)
print(pi*r**2)
print(4/3*pi*r**3)
```

## 6. Numbers

`Python` can store numbers in multiple ways: as integers (`int`), as decimals (`float`) or as strings. It's usually preferable to use integers, as `float`s only use a default amount of precision. Python can hold and use extremely large numbers (even though some other languages need specific support for long integers). When using very small floats in calculations, such as for statistics, be aware that the lack of precision might affect the outcome of the calculations.

The `type` of an object is how `Python` is storing that information.

`Python` allows you to perform arithmetic operations on numbers of mixed types.

```python
print( 12, type(12) )
>>>> 12 <class 'int'>
print( 3.14, type(3.14) )
>>>> 3.14 <class 'float'>
print( 4/2, type(4/2) )
>>>> 2.0 <class 'float'>
print( 4//2, type(4//2) )
>>>> 2 <class 'int'>
print( 9., type(9.))
>>>> 9.0 <class 'float'>
```

### Exercise

Predict the type of each of these expressions, and then check using `type()`.

```python
exp1 = 2 + 3
exp2 = 2. + 3
exp3 = 1/3 + 2/3
exp4 = 1//3 + 1//3
exp5 = 9**0.5
```

## 7. Booleans

A Boolean value is `True` or `False`. You can perform operations using these variables. We will study these in more depth later.

### Exercise

Answer the following questions with either `True` or `False`.

```python
# Every prime number is odd.
answer1 = 

# If a number is divisible by 5 then its last digit is 0 or 5.
answer 2 =
```

## 8. Changing data types

You will sometimes want to change the type of a number.

1. `int(x)` turns `x` into an integer. If `x` is a decimal, then it rounds towards 0.
2. `float(x)` turns `x` into a float.
3. `str(x)` turns `x` into a string.

Remember that you can use `type()` to determine the type of an object.

### Exercise

Find examples of `h` and `b` where these two area formulas are different.

```python
h = 
b = 
area1 = int(b*h/2)
area2 = b*h//2
```

## Project

Here are two projects to test your skills!

### Project 1 - Golf

See the file named `Golf.md` in this folder.

### Project 2 - Project Euler Problem 6

Go to the [Project Euler website to see problem 6](https://projecteuler.net/problem=6). Devise a plan and then code a solution. You will need to use some mathematical thinking to simplify the calculations. Find a solution for a general `n`, then apply it to the special case `n=100`.
