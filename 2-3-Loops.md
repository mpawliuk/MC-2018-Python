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

small_numbers = 0
large_numbers = 0
for trial in range(10):
	x = random.random()
	if x < 0.5:
		small_numbers += 1
	else:
		large_numbers += 1
print(small_numbers, large_numbers)
		
```

When nesting `for` loops, be aware that the runtime of the code will quickly add up. Each loop *multiplicatively* contributes the number of elements it is looping over. So for example, the following code will require `100*200*300` = `6 000 000` steps.

```python
for a in range(100):
	for b in range(200):
		for c in range(300):
			pass
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

## Project 1 - Produce Fibonacci numbers.

In our sample code for section 8, we saw how to find the first Fibonacci number above 1000. Write code (or adapt that code) to produce the 10000th fibonacci number. Write your code as a function `fibonacci(n)` which finds the `n`th Fibonacci number, and then run your code on `n = 10000`. Be sure to test your code with small `n` as well!

## Project 2 - Project Euler Problem 2.

Write a solution to [Project Euler Problem 2](https://projecteuler.net/problem=2) which involves the sum of Fibonacci numbers.

## Project 3 - Project Euler Problem 8.

Write a solution to [Project Euler Problem 8](https://projecteuler.net/problem=8) which involves finding the largest product in a grid. Here is formatted data from the problem statement:

```python
grid = ["73167176531330624919225119674426574742355349194934",
		"96983520312774506326239578318016984801869478851843",
		"85861560789112949495459501737958331952853208805511",
		"12540698747158523863050715693290963295227443043557",
		"66896648950445244523161731856403098711121722383113",
		"62229893423380308135336276614282806444486645238749",
		"30358907296290491560440772390713810515859307960866",
		"70172427121883998797908792274921901699720888093776",
		"65727333001053367881220235421809751254540594752243",
		"52584907711670556013604839586446706324415722155397",
		"53697817977846174064955149290862569321978468622482",
		"83972241375657056057490261407972968652414535100474",
		"82166370484403199890008895243450658541227588666881",
		"16427171479924442928230863465674813919123162824586",
		"17866458359124566529476545682848912883142607690042",
		"24219022671055626321111109370544217506941658960408",
		"07198403850962455444362981230987879927244284909188",
		"84580156166097919133875499200524063689912560717606",
		"05886116467109405077541002256983155200055935729725",
		"71636269561882670428252483600823257530420752963450"]
```

## Project 4 - Prime sieve.

Write code that finds all primes less than 1000 by using a [sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes). We learned about this in our Number Theory class last week. Write your code so that it accepts a general `n`, and then try the special case of `n = 1000`.

Save this code somewhere, and leave helpful comments for yourself, because it it very helpful for many Project Euler problems!
