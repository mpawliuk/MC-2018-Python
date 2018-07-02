# 1-2. Strings and Printing

In this lesson we'll learn the basics of handling strings.

## Outline

1. Escaping characters
2. Basic string concatination (`+`)
3. Index and Truncating
4. String methods (`.upper()`, `.lower()`, `len()`, `.replace()`, `.find()`)
5. String replacement formatting (`.format()`)
6. Input from the user (`input()`)

Project: Madlibs.    
Project: Area of a regular polygon.

## 1. Escaping characters

When using strings, some characters mess with the code. Things like `'`, `"` and `\` get used in English sentences, but to include them in strings we need to **escape** the character with a backslash `\`.

### Exercise

Fix the following code by escaping the problem characters.

```python
greeting = 'Let's make math today!'
response = "My friend said, "that's a good idea."."
hashtag = "#YOLO"
print(greeting, response, hashtag)
```

## 2. Basic string concatination (`+`)

To concatenate ("chain together") strings we use the `+` operation. Make sure that you are adding `string`s together; if you try to add a string and an integer you will get a `type error`.

```python
first_name = "Frances"
middle_name = "E."
last_name = "Allen"
year = 1932

full_info = first_name + " " + middle_name + " " + last_name + ". Born in " + str(year) + "."

print(full_info)
>>>> Frances E. Allen. Born in 1932.
```

This way of formatting sentences is tedious and hard to read, but we'll see a better way of formatting sentences in section 5.

### Exercise - Displaying results of code

You have run a program that looks for large [Pythagorean triples](https://en.wikipedia.org/wiki/Pythagorean_triple). Your code has found one after running for about a while.

Print out a sentence (`display_info`) that displays your triple and the number of minutes it took (rounded to the nearest minute). Make the sentence readable in English.

```python
x = 18108
y = 252685
z = 253333
time = 1143.45369 # In seconds

display_info = "" # Your code here.

print(display_info)
```

## 3. Index and Truncating

You can extract letters from a string by their index. You can extract substrings using `x[start:end]` notation. Counting starts at `0`. If you use negative numbers then you count from the right.

```python
name = "Ursula the Coder"
print(name[0], name[7], name[11])
>>>> U t C
first_name = name[:6]
middle_name = name[7:9]
last_name = name[-5:]
print(first_name, last_name)
>>>> Ursula Coder
```
You can find the index of a character in a string by calling `x.index(character)`. This will give you the first instance of the character in the string if it exists.

```python
name_id = "Shafi Goldwasser"
space_index = name_id.index(" ")
first_name = name_id[:space_index]
last_name = name_id[space_index+1:]
print(first_name)
>>>> Shafi
print(last_name)
>>>> Goldwasser
```

### Exercise - Sensitive Credit Card Numbers

You are in charge of handling sensitive data. For each of these credit card numbers you need to replace the inner 8 digits with `*`s. For example, `4520 1234 5678 0001` should become `4520 **** **** 0001`. 

```python
card1 = "1234 5678 9876 5432"
card2 = "5412 7501 2345 0987"
card3 = "4000 1234 5678 9010"
```

### Exercise - Sensitive Email Adresses

You are again in charge of handling sensitive data, but this time it's with email addresses. For each of these emails you need to replace the user name with 5 `*`s, except for the first letter. For example, `ursula_the_coder@bad.programming.com` should become `u*****@bad.programming.com`. Use the `.index()` method since the emails have different lengths.

```python
email1 = ada_lovelace@computing.uk
email2 = grace.m.hopper@us.gov.com
email3 = evelyn_boyd_granville@IBM.computing.com
```

## 4. String methods (`.upper()`, `.lower()`, `len()`, `.replace()`, `.find()`)

Strings have lots of built-in methods you can perform on them. The most useful one is `len(x)` which returns the length of `x`.

`x = "Ursula the Coder"`|result
----|----
`len(x)` | 16
`x.upper()` | `URSULA THE CODER`
`x.lower()` | `ursula the coder`
`x.replace("e", "*")` | `Ursula th* Cod*r`
`x.find("the")` | 8
`x.count(' ')` | 2

There are [many other string methods](https://docs.python.org/3/library/stdtypes.html#string-methods) you can use. If you need to perform a common task on strings you should look to see if there is a method for it!

### Exercise

It's often very useful to know how many digits a number has. Using the tools we have so far, find the number of digits of the following numbers. `int`s do not have a `len()` method, so you won't be able to just take `len(143)`. However, `string`s do have a `len()` method...

```python
n1 = 314159 #
n2 = 7442000000 # Population of the Earth, 2016
n3 = 2**2**2**2**2 # Make a guess first
```

## 5. String replacement formatting

The best way to insert many variables into a string is by using **string replacement** formatting.

```python
first_name = "Frances"
middle_name = "E."
last_name = "Allen"
year = 1932

full_info = "{} {} {}. Born in {}.".format(first_name, middle_name, last_name, year)

print(full_info)
>>>> Frances E. Allen. Born in 1932.
```

Here is a table of the formatting:

symbol| converts to
---|---
`s` | string
`d` | integer
`f` | float
`.2f`| float, with 2 points of accuracy
`.4s` | string, only first 4 characters

This formatting [is very flexible](https://www.digitalocean.com/community/tutorials/how-to-use-string-formatters-in-python-3), but this is about all we will need.

### Exercise - Displaying results from code (part 2)

Let's look at a previous exercise where we wanted to display the results of code we ran to find Pythagorean triples. Display the results of the code by **using string formatting** as above. This time, when displaying the time, use minutes and give accuracy to within 0.05.

```python
x = 18108
y = 252685
z = 253333
time = 1143.45369 # In seconds

display_info = "" # Your code here.

print(display_info.format())
```

## 6. Input from the user (`input()`)

To prompt the user for keyboard input use `input()`. This will assume the user is giving a `string`, so you may want to adjust the type of the input by wrapping it in a function like `int( input() )`.

You can prompt the user with text by including it in the argument, `input(text)`.

```python
name = input("What is your name, human?")
---> Ursula
job = input("What is your dream job, human?")
---> coder
print( "Hello {}! I also want to be a {}.".format(name, job) )
>>>> Hello Ursula! I also want to be a coder.
```

### Exercise

Ursula has written a calulator that computes the perimeter of a rectangle. Unfortunately, it has a bug in it. Please help her fix it!

```python
w = input("Width of rectangle =")
h = input("Height of rectangle =")

print(w+w+h+h)
```

## Project: Madlibs.

In this project you will make a Madlib. A Madlib is a word game where one player is prompted to give an ordered list of words (usually nouns, adjectives, verbs) without seeing the rest of the text. Once all the words have been chosen, they are inserted into the text, with silly results.

* A noun is a person, place or thing. e.g. Mike, classroom, bicycle.
* An adjective is a describing word. Fast, smart, slimy.
* A verb is an action word. Jump, slurp, roll.
* An adverb modifies a verb or an adjective. Quickly, well, smartly.

For example, choose a `noun` and an `adjective`. Now place them in this text:

> I was late for my Python class today because I forgot my [---*noun*---] in my room. It got very messy and [---*adjective*---]

Your task is to use string replacement and user input to create a madlib game. You can use [this math-themed Madlib](https://www.woojr.com/wp-content/uploads/2017/07/math-madlibs.jpg) as inspiration, or use it directly. After you've made it, upload it to the common folder for others to play.

## Project: calculator

In this project you will create a calculator for the area of a regular polygon with `n>2` sides if you know the side length `s`. Allow the user to supply `n` and `s`. Then give an English sentence reply with the area.

This [wikipedia page](https://en.wikipedia.org/wiki/Apothem) should help you find the area formula for a regular polygon. You will use the `math` package. We will learn more about packages later.

```python
import math

pi = math.pi # This is 3.14159...
math.tan() # Insert an argument to use tan
```
