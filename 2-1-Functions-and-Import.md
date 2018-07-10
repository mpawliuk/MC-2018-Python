# 2-1. Functions, Import, Random, math.

Code gets reused over and over, so we use functions and packages to manage our saved code. A function will serve a single function, like outputing the smallest number in a list, or formatting a paragraph, or printing out the first 10 primes.

Packages are collections of functions that have been written by others that we can access. These include the tools for mathematical operations (using the `math` package), tools for using stats (`numpy`) or accessing random numbers (`random`).

## Outline

1. Structure/purpose of functions (`def`, docstring, body, `return`)
2. Arguments, parameters (scope)
3. Functions without outputs
4. Built-in functions (`min()`, `max()`, `abs()`, `len()`)
5. Import (`from`/`import`, `random`, `math`)
6. Math module (`sqrt`, `factorial`, `e`, `log`)
7. Random module (`.randint(a, b)`, `.random()`, `.uniform(a,b)`, `.seed()`)
8. Other modules. (`dir()`, `datetime`, `time`, `itertools`)

**Project**: Compute e randomly by trials.

## 1. Structure/purpose of functions (`def`, docstring, body, `return`)

A function is a block of code that takes in some data (called **arguments**) and outputs (or `return`s) something. Here is a simple function that returns the average of two numbers.

```python
def average(a, b):
    """Return the average of two numbers a, b as a float."""
    return (a+b)/2
```

The first line starts with `def` which tells Python that we are defining a function. The name of the function is up to you, but make it decsriptive and readable. The input arguments `(a,b)` are contained in the paranthesis; you can have 0 arguments, or as many as you like. The **body** of the function is indented, and is where the code goes. 

The first line of the body is always a commented string called the **docstring**; it always answers the question ``Hey function, what will you do?". Use grammar like `"""Give the average..."""` as opposed to `"""This gives the average"""`. Docstrings can be multiple lines.

The function can have many lines in its body, but it should have at least one `return` which tells it what to output. A function will stop running as soon as it hits a `return`. It is best practice to have each thing that could be returned be of the same `Type`.

```python
def snarky_welcome(n):
    """Give a snarky comment about the user's age."""
    if n <=0:
        return "You are lying!"
    elif n < 18:
        return "Aren't you too young to know computers?"
    elif n < 1000:
        return "Old."
    else:
        return "Wow, I'm actually impressed."
    
print( snarky_welcome( int(input("What is your age?")) ) )
-> 27
>>>> Old.
```

Functions are very flexible! They can output many different things.

To use a function (or *call* it). You write the name of the function with your favourite inputs.

```python
def average(a, b):
    """Return the average of two numbers a, b as a float."""
    return (a+b)/2
print( average(1,3) )
>>>> 2
print( average(-1,3) )
>>>> 1
```

### Exercise 1

Write a function called `four_sum` that takes in four arguments and outputs the sum of all four numbers. Make sure you include a correctly written docstring.

```python

# Your code here
#
#

# Don't modify this!
if four_sum(-1, 0, 1, 9) == 9 and four_sum(0,0,0,0) == 0:
    print("Great work!")
else:
    print("Something went wrong!")
```

### Exercise 2

Write a function called `triangular_number` that takes in a number `n` and outputs the [nth triangular number](https://en.wikipedia.org/wiki/Triangular_number).

## 2. Arguments, parameters (scope)

When writing a function, you can define new variables that only appear in the body of the function; these are called **local variables** and should only be used inside the function where they are introduced. If you try to call a local variable outside a function you will get an `Error`.

**Global variables** are variables that appear in your code outside your functions. Functions cannot modify global variables directly.

These are issues about the **scope** of a variable.

```python
def average(a, b):
    """Return the average of two numbers a, b as a float."""
    x = a + m # Local variable
    return x/2

print(x)
>>>>Traceback (most recent call last):
>>>>  File "python", line 6, in <module>
>>>>NameError: name 'x' is not defined
```

Here is an example of a function trying to modify a global variable and failing.

```python
intensity = 1

def increase_intensity():
    """Increase the intensity by 1."""
    intensity += 1
    return None

increase_intensity()
>>>> Traceback (most recent call last):
>>>>  File "python", line 8, in <module>
>>>>  File "python", line 5, in increase_intensity
>>>> UnboundLocalError: local variable 'intensity' referenced before assignment
```

Sometimes we want to define a function, but we don't exactly know how many input variables it will take. Python is flexible enough to allow that. By using the `*args` or `*rest` argument.

```python
def remove_second_element(a,b, *args):
    """Print the same elements without the second item."""
    print(a, *args)
    return None

remove_second_element(1,2,3,4,5)
>>>> 1 3 4 5
```

We can also set default values for arguments. These will be used if not otherwise specified. This can be helpful for debugging.

```python
def average(a, b=1):
    """Return the average of two numbers a, b as a float.
    If not specified, then b will be 1.
    """
    return (a+b)/2
print( average(5) )
print( average(1,3) )
```

### Exercise

Write a function called `divide` that takes in two arguments `p`, `q`, and returns their division `p/q`. Set the default value for `q` to be 1. Also, only perform the division if `q` is not 0 (in which case you should `return` a passive-aggressive message to the user). 

## 3. Functions without outputs

Functions don't have to `return` anything useful, they can do some other things (like printing) then return the object `None`. If you forget to include a `return` statement in your function it will automatically return `None`.

```python
def print_age(year_of_birth, current_year=2018):
    """Give the age of the user."""
    age = current_year - year_of_birth
    print("You are {} years old.".format(age))
    return None
print_age(1987)
>>>> You are 31 years old.
```

## 4. Built-in functions (`min()`, `max()`, `abs()`, `len()`)

Python has many functions already built in that you can access. Here are some of them:

function | What it does
----|----
`min( *args )` | Give the minimum value in `*args`
`max( *args )` | Give the maximum value in `args`  
`abs( n )` | Give the absolute value of `n` 
`len( word )` | Return the number of characters in `word`

Sometimes these can only be applied to numbers, sometimes they can be applied to strings and lists (which we'll see later).

```python
print( min(2,4,6,-1, 8) )
>>>> -1
print( min('w', 'l', 'z') )
>>>> l
print( min('ursula') )
>>>> a
print( abs(-10) )
>>>> 10
print( len('Math Circle') )
>>>> 11
```

### Exercise

Write a function `median(a, b, c)` that returns the median of three numbers. (The median of three numbers is the number that is neither the largest, nor the smallest.) For example, the median of 1,5, and 4 is 4. 

```python

# Your code here
#
#

# Don't modify this!
if median(3,3,3) == 3 and median(-1, 3, 2) == 2 and median(3,2,2) == 2:
    print("Great work!")
else:
    print("Something went wrong!")
```

## 5. Import (`from`/`import`, `random`, `math`)

Many people have written **modules**, **packages** and **libraries** that Python can access and use when needed. They need to be `import`ed at some point in your code (usually the beginning of the code). For a complete overview, including installing missing modules, [see this write-up](https://www.digitalocean.com/community/tutorials/how-to-import-modules-in-python-3).

A module is essentially just a `.py` file that is a list of coded functions. So you can also import functions from your own other files if you want. Importing previously named functions might cause conflicts, so often we will only import specific functions that we need.

```python
import math
print(math.e)
>>>> 2.718281828459045
print(math.pi)
>>>> 3.141592653589793
print(math.factorial(4))
>>>> 24
```

Compare with just importing some functions. We will get an error when we call `math.factorial` because we did not import `math`.

```python
from math import e, pi
print(math.e)
>>>> 2.718281828459045
print(math.pi)
>>>> 3.141592653589793
print(math.factorial(4))
>>>> Traceback (most recent call last):                                                                                                   
>>>>  File "/home/main.py", line 6, in <module>                                                                                          
>>>>    print(math.factorial(4))                                                                                                         
>>>> NameError: name 'math' is not defined
```

Another commonly used module is `random` which is used to call random numbers.

```python
import random
print( random.randint(0,10) )
print( random.randint(0,10) )
print( random.randint(0,10) )
```

## 6. Math module (`sqrt`, `factorial`, `e`, `log`)

The math module has access to many handy function and constants. The trig functions are all there, as are exponentials, logs and squareroot.

function | Effect
----|----
`sqrt(x)` | Square root of x
`factorial(n)` | `n! = n*(n-1)*...*2*1`
`e` | Euler's constant
`log(x, base)` | log(x) to a given `base`
`exp(x)` | e to the power x
`gcd(a,b)` | The greatest common divisor of a,b

There are many others included. [Check the documenation for a full list](https://docs.python.org/3/library/math.html).

### Exercise

Explain what is going on in this example:

```python
import math

half_pi = math.pi/2
print( math.tan(half_pi) == 0 )
>>>> False
```

## 7. Random module (`.randint(a, b)`, `.random()`, `.uniform(a,b)`, `.seed()`)

The `random` module is very fun. It can be used to choose random integers, or numbers from a range, or elements from a list/string (coming soon!).

Function | Effect
----|----
`randint(a,b)` | Give a random integer between a and b inclusive
`random()` | Give a random float between 0 and 1
`uniform(a,b)` | Give a random flaot between a and b
`choice( x )`| Give a random element of x

When debugging or writing the initial code, it can be useful to use a fixed `seed()` which will allow the code to choose randomly the same way each time.

```python
import random

random.seed(17856) # Sets the seed
x = random.random()
print( x )
>>>> 0.23210147625761968
```

## 8. Other modules. (`dir()`, `datetime`, `time`, `itertools`)

The other modules we will use very often are `time` and `itertools`.

The `time` module allows us to access the system timer, which can be used to time programs.

```python
import time
start = time.time()

print( len( str(9**99999) ))
>>>> 95424                                                                                                                                
end = time.time() - start
print( "This took {0:.4f} seconds to run.".format(end) )
>>>> This took 0.1585 seconds to run.
```

The `itertools` module is what is used to produce all permutations, combinations and products of a set. I use this a lot!

```python
import itertools
print( list(itertools.permutations('abc', 3)))
>>>> [('a', 'b'), ('a', 'c'), ('b', 'a'), ('b', 'c'), ('c', 'a'), ('c', 'b')] 
```

You can call the directory of a module which will tell you all its contents. You can also call the docstring `.__doc__` of individual functions to hear what they do.

```python
import math
print( dir(math) )
>>>> ['__doc__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 
'copysign', 'cos', 'cosh', 'degrees', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gam
ma', 'hypot', 'isfinite', 'isinf', 'isnan', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'pi', 'pow', 'radians', 'sin'
, 'sinh', 'sqrt', 'tan', 'tanh', 'trunc']

print( math.log.__doc__ )
>>>> log(x[, base])                                                                                                                       
>>>>                                                                                                                                     
>>>> Return the logarithm of x to the given base.                                                                                         
>>>> If the base not specified, returns the natural logarithm (base e) of x. 
```

### Exercise

Play around with the `datetime` module. See what you can do with it by calling its directory.

## Project: Estimate `e`

It's known that if you can approximate `e` by sampling real numbers between 0 and 1 and keeping track of how many numbers you take for their sum to pass 1. [See here for a full discussion](https://stats.stackexchange.com/a/194143). For each trial you'll get an `n` for the number of real numbers it took to cross 1. The average of all of these n should be close to e.

We don't have very many tools yet to simulate this, but we can do some of it. Perform 10 trials of this experiment and see how close your everage is to e. Later we will have more sophisticated methods of automating this.
