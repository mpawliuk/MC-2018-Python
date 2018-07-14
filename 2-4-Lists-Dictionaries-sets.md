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

**Project**: Project Euler Problem 20, Prime Factor decomposition

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



## 3. Dictionaries: Keys and values
4. Defining dictionaries explicitly, by value, by comprehension
5. Dictionary Methods (`.keys()`, `.values()`, sorting)
6. Sets: (Defininition, what they are used for, unordered)
7. What can go in a set?
8. Getting the number of unique elements of a list.

**Project**: Project Euler Problem 20, Prime Factor decomposition
