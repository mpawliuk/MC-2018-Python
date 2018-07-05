# 1-3. Conditionals and Control Flow

Today we learn how to tell the computer to make decisions and comparisons. This allows us to give complicated sets of instructions that can change depending on the input.

## Outline

1. Comparisons, (`==`, `!=`, `<`, `>`, `<=`, `>=`)
2. Logical operators(`and`, `or`, `not`) 
3. Conditionals (`If`/`else`, `elif`, indents, formatting)
4. How Python treats non-Booleans

Project: Project Euler 1 (part 1)    
Project: Pig Latin translator.

## 1. Comparisons, (`==`, `!=`, `<`, `>`, `<=`, `>=`)

The four basic comparisons take in two numbers (`int` or `float`, you can mix them) and outputs the Boolean `True` or `False`.

code | words
---|---
`<` | less than
`<=`| less than or equal to
`>` | greater than
`>=`| greater than or equal to

For example

```python
print(6 > 5, 6 >= 5, 6 < 5, 5 <= 5)
>>>> True True False True
```

We already use `=` for variable assignment, so we use `==` for equality and `!=` for not equal. Objects of different types, but with the same value are considered equal, e.g. `1 == 1.0`.

code | words
---|---
`==` | equal
`!=`| not equal

```python
print(6 == 5, 5 == 10/2, 6 != 5, 5 != 10/2)
>>>> False True True False
```

Be careful when comparing `float`s as numerical imprecision might make Python believe things are not equal when in fact they should be.

```python
import math
pi = math.pi
print(math.tan(pi/4), 1, math.tan(pi/4) == 1)
>>>> 0.9999999999999999 1 False 
```

2. Logical operators(`and`, `or`, `not`)

We can combine simple statements to make more complicated expressions by connecting statements with logical operators:

operator | output
---|---
`x and y` | `True` only when both `x` and `y` are `True`
`x or y` | `True` as long as at least one of `x` or `y` are `True`
`not x` | `True` if `x` is `False`, and `False` if `x` is `True`

For example:

```python
x = 6 > 5
y = 5 > 9
z = 2 < 0
print( x and y, x or y, not z)
>>>> False True True
```

Things get more complicated when we chain together logical operators. We could spend a long time discussing combinations of logical operators, but here we'll only mention the basics. Operations are performed in the following order:

1. `not`
2. `and`
3. `or`

For example:

```python
x = 6 > 5
y = 5 > 9
z = 2 < 0

print( x and y or x and not z)
>>>> True
```

### Exercise

Ursula has written some code that checks if a number is in a certain range. Her code is horrible. Please help fix it.

```python
n = 7
x = n < 5
y = 10 < n

print( not not not not not (x and y) )

```

## 3. Conditionals (`if`/`else`, `elif`, indents, formatting)

The conditional `if` statements run code if a condition is `True`. The code to run is indented by a tab.

```python

# We are going to buy some groceries
wallet = 10
items_purchased = 0

if wallet >= 3:
	# Buy eggs
	items_purchased += 1
	wallet -= 3
if wallet >= 4:
	# Buy milk
	items_purchased += 1
	wallet -= 4
if wallet >= 2:
	# Buy celery
	items_purchased += 1
	wallet -= 2
if wallet >= 5:
	# Buy ice cream
	items_purchased += 1
	wallet -= 5

print("You bought {} items, and have {} dollar(s) left.".format(items_purchased, wallet))
>>>> You bought 3 items, and have 1 dollar(s) left."
```

An `if` statement can be followed by an `else` statement, which runs only when the `if` statement is `False`.

```python

n = 7

if n%2 == 0:
	print("{} is even.".format(n))
else:
	print("{} is odd.".format(n))
>>> 7 is odd.
```

For multiple cases you can use `elif` ("else if") which also checks a condition.

```python

n = 7

if n%2 == 0:
	print("{} is even.".format(n))
elif n%4 == 1:
	print("{} is 1 more than a multiple of 4.".format(n))
else:
	print("{} is 3 more than a multiple of 4.".format(n))
```

You can nest `if` statements, but be careful that your code stays readable.

```python

# Try other choices for n and m to get each of A,B,C,D to appear.
n = 10
m = 2

if n:
	if m:
		print("A", n/m, m/n)
	else:
		print("B", m/n)
else:
	if m:
		print("C", n/m)
	else:
		print("D")

```

## 4. How Python treats non-Booleans

When using `if` statements, Python is very flexible. You can pass strings or numbers to the `if` statement, not just Booleans. A number is evaluated as `False` if it is `0`, and it is `True` otherwise. A string is evaluated as `False` if it is the empty string, and `True` otherwise.

This allows for more readable code and allows us to shorten statements like `if x == True:` to `if x:`. 

For example:

```python
count = 2
count -= 1
count -= 1

if count:
	# we can divide by 0
	print(10/count)
else:
	# count is 0
	print("We can't divide by 0.")
>>>> We can't divide by 0.
```

### Exercise

Rewrite the example code from part 3 so that it doesn't use `==`. You may have to reorder the code.

```python
# Example code from section 3.

n = 7

if n%2 == 0:
	print("{} is even.".format(n))
else:
	print("{} is odd.".format(n))
>>> 7 is odd.
```


## Project: Project Euler 1 (part 1)    

In this project you will write the code for a large portion of [Project Euler Problem 1](https://projecteuler.net/problem=1) (we'll complete the code next week). Here's the statement of the problem:

> If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

> Find the sum of all the multiples of 3 or 5 below 1000.

We will solve this question by looping over all numbers between 1 and 1000, and adding it if it satisfies the criteria (a multiple of 3 or 5). We don't know how to loop yet, so for now, you should write the part of the code that:

1. Declares a variable `total` that will keep track of the sum so far. (What should you initialize it as?)
2. Checks if `n` is a multiple of 3 or 5.
3. Adds `n` to the `total` if it is.

Test your code on a variety of numbers to see if it works the way you think it should.

**Note**. This Project Euler problem can be solved by hand, without a computer. Try it if you want!

## Project: Pig Latin translator.

In this project you will create code that translates English words into Pig Latin. To translate a word into Pig Latin you follow these rules:

1. For words that begin with consonant sounds, all letters before the initial vowel are placed at the end of the word sequence. Then, "ay" is added, as in the following examples: "pig" = "igpay", "latin" = "atinlay".
2. When words begin with consonant clusters (multiple consonants that form one sound), the whole sound is added to the end when speaking or writing. "smile" = "ilesmay", "string" = "ingstray".
3. For words that begin with vowel sounds, one just adds "ay" to the end. Examples are: "eat" = "eatay", "omelet" = "omeletay".

You can find the full rules of [Pig Latin here](https://en.wikipedia.org/wiki/Pig_Latin#Rules), along with many more examples.

Your task is to write code that turns a single `word` into Pig Latin (as `pl_word`). Once you've done that, you can insert your code into the following code which translates a full sentence.

```python

plain_text = "The quick brown fox jumps over the lazy dog."
cipher_text = ""

for word in plain_text.split():
	# Your code here. You need to translate the string in the variable "word". 
	# Leave the translated word as pl_word.
	#
	cipher_text += pl_word
	cipher_text += " "

print(cipher_text)
```
