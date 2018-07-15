# 2-4.  Lists, Dictionaries and Sets

We introduce two additional data types that often appear when dealing with mathematics: dictionaries and sets. Sets allow us to store information when we don't care about order or quantity, only whether something is in a set or not. Dictionaries allow us to store similar information while also keeping track of quantity or additional qualities.

## Outline

1. List comprehesion 1. (using `for`)
2. List comprehension 2. (using `if`)
3. Dictionaries: Keys and values
4. Defining dictionaries explicitly, by value, by comprehension
5. Dictionary Methods (`.keys()`, `.values()`, sorting)
6. Sets: (Defininition, what they are used for, unordered)
7. What can go in a set?
8. Getting the number of unique elements of a list.

**Project**: Project Euler Problem 47, Prime Factor decomposition

## List comprehesion 1. (using `for`)

Many lists can be defined in a compact way by using **list comprehension**. When possible, you should use list comprehension.

```python

# Good - list comprehension
squares = [x**2 for x in range(10)]
print( squares )
>>>> [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# Worse
squares = []
for x in range(10):
  squares.append(x**2)
print( squares )
>>>> [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

### Exercise

Create a list called `shifted_primes`, using list comprehension, of all the `primes`, but multiply each prime by `100`, and then add the `prime` squared to it.

```python
primes = [2, 3, 5, 7, 11, 13, 17, 19]
shifted_primes = [] # <- Your code here. 
```

## 2. List comprehension 2. (using `if`)

List comprehension can also contain a conditional `if` statement. Elements will only be added to the list if they satisfy the condition. The `for` part comes first, and the `if` part comes after; you will likely to forget this, so look it up in the Python documentation whenever you need a reminder. 

```python
odd_squares = [x**2 for x in range(1,10) if x % 2] # Remember x % 2 != 0 when x is odd
print(odd_squares)
>>>> [1, 9, 25, 49, 81]
```

### Exercise

You have data about how many math problems each person in the class has completed. Using list comprehension, make a list `most_exercises` which contains the names of the students who have completed more than 10 problems.

```python
students = [ ["Ethan", 12], ["Lizette", 19], ["Tara", 24], ["Oskar", 3] ]
instructors = [ ["Mike", 97], ["Brian", 568] ]

most_exercises = [] # <- Your code here
```

## 3. Dictionaries: Keys and values

Lists of lists can store complex information, but it is often more natural to store this information as a `dictionary`. A dictionary is often a better way of doing this. It does not keep track of order.

The `keys` are the names of the entries (name, age, location) the values are the actual entries (Mike, 30, Calgary). You can call an entry by using the formatting `dict[key]`.

```python
mike_info = {"name": "Mike", "age": 30, "location": "Calgary"}
print( mike_info["age"] )
>>>> 30
```

### Exercise

Fill in an entry for your own information, similar to `mike_info`. Include at least one additional key.

```python
mike_info = {"name": "Mike", "age": 30, "location": "Calgary"}
```

## 4. Defining dictionaries explicitly, by value, by comprehension

Dictionary values can be set by using the formatting `dict[key] = value`. When the key already exists, then you can use `dict[key] += 1` to increment the value.

```python
prime_decomp = {} # We will make the prime decomposition of 840 = 2 * 2 * 2 * 3 * 5 * 7. 
prime_decomp[2] = 3
prime_decomp[3] = 1
prime_decomp[5] = 1
prime_decomp[7] = 1

print( prime_decomp )
>>>> {2: 3, 3: 1, 5: 1, 7: 1}
```

Dictionaries can also be defined in a similar way to list comprehension.

```python
students = ["Yana","John","Andrew","Tara","George","Maxim","Devanshu","Max","Vishnu","Adrien","Audrey","Sophia","Joy","Lizette","Oskar","Will","Ethan"]
names = { person: len(person) for person in students}
print( names )
>>>> {'Yana': 4, 'John': 4, 'Andrew': 6, 'Tara': 4, 'George': 6, 'Maxim': 5, 'Devanshu': 8, 'Max': 3, 'Vishnu': 6, 'Adrien': 6, 'Audrey': 6, 'Sophia': 6, 'Joy': 3, 'Lizette': 7, 'Oskar': 5, 'Will': 4, 'Ethan': 5}
```

### Exercise

Define a dictionary called `attendance` whose keys are `number_theory`, `python`, `stats` and `combinatorics`. The values of these keys should be the number of students in each of these classes for QTM Math Circle 2018 (make an educated guess).

## 5. Dictionary Methods (`.keys()`, `.values()`, sorting)

You can access the keys of a dictionary with `.keys()` and you can access the values by `.values()`.

```python
print( mike_info.keys() )
>>>> dict_keys(['name', 'age', 'location'])
```

You can also sort a dictionary by its keys.

```python
students = ["Yana","John","Andrew","Tara","George","Maxim","Devanshu"]
names = { person: len(person) for person in students}

for person in sorted(names.keys()):
  print( person, names[person] )
>>>> Andrew 6
>>>> Devanshu 8
>>>> George 6
>>>> John 4
>>>> Maxim 5
>>>> Tara 4
>>>> Yana 4
```

### Exercise

Write a function that takes in a dictionary of the prime decomposition of a number and returns the number itself. For example, `number( {2: 3, 3: 1, 5: 1, 7: 1} )` should output `840`.

## 6. Sets: (Defininition, what they are used for, unordered)

A set is similar to a list, except the order does not matter, and there cannot be repeated items. There are some technical reasons to use sets, but for now, just believe that they are easier for Python to handle than lists. The order of elements in the set are not preserved.

```python
# n = 840
prime_factors = {2,3,5,7}
print ( prime_factors )
>>>> {2,3,5,7}
```

## 7. What can go in a set?

Sets can hold strings and numbers, but cannot hold lists, dictionaries or other sets.

## 8. Getting the number of unique elements of a list.

Often times you will want to figure out the unique number of elements in a list. This can be done by first turning your list into a set, using `set()`, then turning it back into a list, using `list()`, then taking its length. Note that you cannot take the length of a set.

```python
prime_decomp = [2,2,2,3,3,5,7]
number_primes = len( list( set(prime_decomp) ) )
print( number_primes )
>>>> 4
```

### Exercise

You have found all primes less than 100 using a method that sometimes produces duplicates. Use Python to output the list of unique primes *in the correct order*.

```python
found_primes = [47, 67, 41, 5, 71, 43, 73, 89, 31, 11, 73, 97, 41, 43, 13, 7, 47, 5, 5, 83, 19, 61, 23, 23, 3, 59, 2, 79, 29, 53, 29, 13, 79, 3, 17, 31, 19, 89, 83, 59, 37, 3, 2, 97, 71, 17, 2, 11, 7, 11, 7, 13, 61, 17, 37, 53, 67]
```

## Project 1: Prime Factor decomposition

1. Write a function that finds the prime factor decomposition of a number $n$.
2. Write a function that finds the unique prime factors of a number $n$. This is the [Prime Omega function](https://en.wikipedia.org/wiki/Prime_omega_function).

Make sure to save these functions as they are very handy to have around!

## Project 2: Project Euler Problem 47

Solve [Project Euler Problem 47](https://projecteuler.net/problem=47), which has to do with the number of unique prime factors of a number $n$. You will probably want to solve the previous project before you do this.
