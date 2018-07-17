# 2.3 Exercises

We have learned a lot of new concepts in Python in the past 6 classes. In order to give you a chance to internalize the ideas and syntax, today will be a day to catch up on exercises from previous days.

My suggestion is to do one of the following:

1. Complete the exercises and projects from previous classes, or
2. Complete some of the exercises I've posted below.
3. Find a project Euler problem that you like. I'll make suggestions below.

## Project Euler suggestions

The most of the problems from 1-20 are all possible given the tools you have. Find one that interests you

* Problems 3,7,10 require you to produce primes, possibly by the Sieve of Eratosthenes.
* Problem 13 requires you to get Python to read text (which we'll do later).
* Problem 14 requires a `while` loop, which we haven't done yet.

All the other problems should be accessible to you. Problem 25 is about large Fibonacci numbers, which should appeal to some of you.

## Bonus exercises

### Exercise 1 - Sorting students

```python
students = ["Yana","John","Andrew","Tara","George","Maxim","Devanshu","Max","Vishnu","Adrien","Audrey","Sophia","Joy","Lizette","Oskar","Will","Ethan"]
```

1. Print `students` but sorted alphabetically.
2. Print the names of the first three `students` alphabetically.
3. Find how many `students` have at least 6 letters in their name.
4. Find the average length of a `students` name.

### Exercise 2 - Pythagorean Triples

In this exercise you will find all small

1. Write a function that takes in three variables `a,b,c` and returns `True` if they sum to more than 10.
2. Write a function that takes in three variables `a,b,c` and return them in increasing order.
3. Write a function that takes in three variables `a,b,c` and returns `True` if they form a Pythagorean triple.
4. Print all numbers i greater than 0, but less than 5.
5. Print all pairs i,j such that 0<=i<=j<5.
6. Print all triples i,j,k such that 0<=i<=j<=k<5.
7. Find all Pythagorean triples `a,b,c` where all values are less than 1000.
8. Solve [Project Euler Problem 9](https://projecteuler.net/problem=9).

### Exercise 3 - Digits!

1. Write a function that takes in a number `n` and returns its number of digits. Use `len()` and `str()`.
2. Write a loop that prints out each digit of a number `n`. You can loop over the characters in a string.
3. Write a loop that adds each digit of a number `n` to a variable `total`. Remember to use `int()`.
4. Put your code together into a function that takes in a number `n` and `return`s the sum of its digits.
5. Solve [Project Euler Problem 16](https://projecteuler.net/problem=16).
6. `import` the math module and compute the number of digits in 10! (Use `math.factorial(10)`.)
7. Solve [Project Euler Problem 20](https://projecteuler.net/problem=20).

### Exercise 4 - A Sieve

In this exercise we will make a sieve of Eratosthenes. Each step will give you an ingredient for your sieve.

1. Print out all multiples of 2 less than 30.
2. Find the squareroot of 30. (You may wish to import math.)
3. Print each number (call it a `slope`) between 2 and the squareroot of 30.
3. Make a list called `primes` that contains the numbers from 2 to 30. (This will
4. Check to see if 14 is in `primes`.
5. If 14 is in `primes`, then remove it.
6. Loop over all even numbers between 3 and 30, check to see if it is still in `primes`, and remove it from `primes` if it is.

Now we have all the tools we need to make a sieve.

1. Define a function `sieve()` that takes in a number `n` and returns all primes between 2 and n.
2. Initialize a list called `primes` of all numbers between 2 and n.
3. Loop over all `slope`s between 2 and the squareroot of n.
4. In each loop, remove all multiples of `slope` from `primes`. (You will probably do this in a loop.)
5. After all the `slope` loops finish, `return primes`.

Check that this works for `n=10`, `n=30` and `n=500`.
