# 2-3. Loops (`for`, `while`)

Today we will unlock the computing power of Python by using repeated instructions. We will be able to repeatedly call a block of code, while possibly changing some variables or parameters each time.

## Outline

1. `for` loop review
2. Looping over strings.
4. Combining `for` and `if`
5. `break`
6. `for`/`else`
7. nested loops (order, good naming, runtime)
8. `while` loop (formatting, indent, infinite loops)
9. `break`
10. `while`/`else` (formatting, when is the else executed)

**Project**: Produce Fibonacci numbers, Prime sieve, Project Euler Problem 2.

## 1. `for` loop review

Recall from last time our most basic loop with `range(n)`. Features include:

* Indent the code you want to repeat
* The `:` to denote the beginning of the repeatable code.
* `variable_name in` a list or an iterator.

```python
for i in range(2,5):
    print(i)
>>>> 2
>>>> 3
>>>> 4
```

You can also loop through lists.

```python
# Add up all primes <= 11.
small_primes = [2,3,5,7,11]
total = 0
for p in small_primes:
    total += p
print( total )
>>>> 28
```

## 2. Looping over strings.

Python is also able to loop over strings. In this case it goes one character at a time in the string.

```python

def aretha_franklin():
	"""Find out what it means to her."""
	for letter in "RESPECT":
		print( letter )
	return None

aretha_franklin()
>>>> R
>>>> E
>>>> S
>>>> P
>>>> E
>>>> C
>>>> T
```

### Exercise

Write a function called `sum_of_digits(n)` that adds up the digits of `n`.

```python

def sum_of_digits(n):
	"""Sum the digits of a number n."""
	total = 0
	### Your code here.
	#
	#
	return total
```

## 3. Taking a `pass`

Every `for` loop in Python must contain *something* to run; the body cannot be empty. In the event that you just need *something*, possibly as a placeholder, you can use `pass`. Python does nothing when it encounters this. This can be helpful when writing the first draft of code.

```python
import time
start = time.time()

# 10**7 = 10 000 000
for i in range(10**7):
	pass
print( time.time() - start)
```

## 4. Combining `for` and `if`

`for` loops and `if` statements can be combined. Just make sure your code stays readable.

```python
# Sum of the even numbers < 100
total = 0
for i in range(100):
	if i%2 == 0:
		total += i
print( total )
```

### Exercise

Print out all multiples of 17 less than 100.

## 5. `break`

Often in math we look for special configurations, or counterexamples by running through all possible sets of data. When we find one, we can `break` the loop to exit it immediately, without using the remaining indicies.

```python

for i in range(100):
	if i**2 > 50:
		print(i, i**2)
		break
```

### Exercise

Find a solution to the following diophantine equation by looping over all `x` and all `y`.

```python
# Solve 17x + 11y = 211
# Assume both x < 20 and y < 20.
```

6. `for`/`else`

`break` statements can be combined with `else` statements which only run if the `for` loop completes. If the `for` loop breaks, then the `else` statement doesn't run.

```python
students = ["peter", "drake", "hannah", "mike", "elle", "vishnu"]

for person in students:
	# x[::-1] reverses the order of x.
	if person == person[::-1]:
		print("The class contains a palindrome name: {}.".format(person) )
		break
else:
	print( "The class contains no one with a palindrome name." )
>>>> The class contains a palindrome name: hannah.
```

### Exercise

Modify the above code with `students.remove()` to make the `else` statement run.

## 7. nested loops (order, good naming, runtime)

`for` loops can be nested. When doing so the first loop will increment once, then the whole inner loop will run.

```python
for i in range(3):
	for j in range(2):
		print(i, j)
>>>> 0 0
>>>> 0 1
>>>> 1 0
>>>> 1 1
>>>> 2 0
>>>> 2 1
```

When running `for` loops, and *especially* when running nested `for` loops, be sure to name your indices in a descriptive way.

```python
import random
for trial in range(10):
	for  in range():
		
```

## 8. `while` loop (formatting, indent, infinite loops)

Another type of loop is the `while` loop, which has the advantage of not having to specify a range of the variable. It runs until some statement becomes false. This means your loop should have some method of actually making that statement false, otherwise it will run forever!

`while` loops are an alternative to for loops that can be easier to use, or more readable, depending on the context. 

```python
fib1 = 1
fib2 = 2
# Find the first Fibonacci number above 1000.
while fib2 <= 1000:
	fib1 += fib2
	fib2 += fib1
print(fib1, fib2)
>>>> 987 1597
```

### Exercise

Ursula has written the following `while` loop, but unfortunately it does not terminate! Add a line in the body of the loop that actually increments the variable.

```python
total = 0
while total < 1000:
	total += 0
```

8. `while`/`break`/`else` (formatting, when is the else executed)

Like `for` loops, `while` loops can also use `break` and `else` statements. In this case the `else` statement will run if the while loops exits via the statement becoming False. If the loop `break`s then the `else` statement will not be run.

```python
import time, random
start = time.time()

while time.time() - start <2 :
	# Runs for 2 seconds or until 0.1234 appears
	x = random.random()
	if x == 0.1234:
		print( "found it!")
		break
else:
	print( "No random number was found equal to 0.1234 after 2 seconds." )
```
