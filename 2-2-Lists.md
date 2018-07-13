# 2-2. Lists

## Outline

1. What can go in lists? (strings, integers, lists)
2. `append()`, `remove()`
3. List methods (`len()`, `max()`, `min()`, `sum()`, `sorted()`, `reverse()`)
4. List splicing and indexing
5. `range(n)`
6. Your first `for` loop
7. `enumerate`, tuples
8. `zip`

## 1. What can go in lists? (strings, integers, lists)

A `list` is a data type in Python that stores objects in a specific order. A list can store strings, integers or even other lists! We can use `in` to ask Python if something is an element of our list.

```python
students = ["Ethan", "Lizette", "Tara", "Oskar"]
instructors = ["Mike", "Brian"]

if "Oksar" in students:
  print("Oskar is a student.")
else:
  print("Oskar is not a student")

if "Tara" in instructors:
  print("Tara is an instructor.")
else:
  print("Tara is not an instructor.")
```

We can also make lists of lists.

```python

student_pairs = [ ["Ethan", "Oskar"], ["Lizette", "Tara"] ]
```

## 2. `append()`, `remove()`

To add items to a list we use `.append()`. To do this we call the method and Python will update the list.

```
students = ["Ethan", "Lizette", "Tara", "Oskar"]

print(students)
>>>> ["Ethan", "Lizette", "Tara", "Oskar"]
students.append("Joy")
print(students)
>>>> ["Ethan", "Lizette", "Tara", "Oskar", "Joy"]
students.append("Joy") # Add Joy again
print(students)
>>>> ["Ethan", "Lizette", "Tara", "Oskar", "Joy", "Joy"]
```

To remove items to a list we use `.remove()`. To do this we call the method and Python will update the list. If you try to remove an item not in the list you will get an `Error`.

```
students = ["Ethan", "Lizette", "Tara", "Oskar"]

print(students)
>>>> ["Ethan", "Lizette", "Tara", "Oskar"]
students.remove("Tara")
print(students)
>>>> ["Ethan", "Lizette", "Oskar"]
students.remove("Joy") # She is not in the class. Error!
print(students)
>>>> Traceback (most recent call last):
>>>>  File "python", line 6, in <module>
>>>> ValueError: list.remove(x): x not in list
```

### Exercise

Ursula has done a sloppy job of trying to find the list of primes under 35. Please remove the composite number in this list and add in the missing prime.

```python
primes = [2,3,5,7,11,13,17,19,21,23,29]
print(primes)
```

## 3. List methods (`len()`, `max()`, `min()`, `sum()`, `sorted()`, `reverse()`)

Like strings, lists have access to many helpful methods.

Function | Effect
----|----
`len(x)`| Number of elements in `x`
`max(x)`| Maximal element of `x`
`min(x)`| Minimal element of `x`
`sum(x)`| Add up all elements of `x`
`sorted(x)`| Put `x` in increasing order
`reverse(x)`| Reverse the current order of `x`

```python
students = ["Ethan", "Lizette", "Tara", "Oskar"]

print( sorted(students) )
>>>> ['Ethan', 'Lizette', 'Oskar', 'Tara']

primes = [2,3,5,7,11,13,17,19,23,29]
print( sum(primes) )
>>>> 129
```

### Exercise 1

The class can hold only 18 students, and Dylan would like to join the class. Check to see if there is room in the class. If there is, then add Dylan to the class.

```python
students = ["Yana","John","Andrew","Tara","George","Maxim","Devanshu","Max","Vishnu","Adrien","Audrey","Sophia","Joy","Lizette","Oskar","Will","Ethan"]
```

### Exercise 2

Write a function that determines the average of a list, then run it on `test_marks`. You should get around `0.30769`.

```python
test_marks = [0,0,1,0,1,0,0,0,0,0,0,1,1]
```

## 4. List splicing and indexing

Much like strings you can call specific elements of a list by calling their index. You can also split up lists using the `x[start:end]` formatting.

```python
students = ["Yana","John","Andrew","Tara",]
print(students[2])
>>>> Andrew
print(students[:2])
>>>> ["Yana","John"]

```

## Exercise

Write a function that randomly splits up a classroom of students into 2 groups of roughly equal size and prints the members of each group. Use the `shuffle()` method from the `random` module. Then run your function to split up `students` into 2 groups.

```python
students = ["Yana","John","Andrew","Tara","George","Maxim","Devanshu","Max","Vishnu","Adrien","Audrey","Sophia","Joy","Lizette","Oskar","Will","Ethan"]
```

## 5. `range(n)`

One very special object in Python is `range(n)` which iterates over all numbers 0,1,2,3, ..., n-1. It stops before n. You can also start at a different index if you like by using `range(start, end)`.

```python
print( list(range(7)) )
>>>> [0, 1, 2, 3, 4, 5, 6]
print( list(range(2, 7)) )
>>>> [2, 3, 4, 5, 6]
```

## 6. Your first `for` loop

You will now see your very first for loop! Hooray. A `for` loop is your basic instruction for asking Python to repeat code.

```python
for i in range(5):
    print(i)
>>>> 0
>>>> 1
>>>> 2
>>>> 3
>>>> 4
```

You can name your index variable whatever you like, but try to keep it descriptive and intuitive.

```python
students = ["Yana","John","Andrew","Tara"]

for person in students:
    print( person + "!")
>>>> Yana!
>>>> John!
>>>> Andrew!
>>>> Tara!
```

### Exercise

Use the tools we have to give a complete answer to [Project Euler Problem 6](https://projecteuler.net/problem=6).

## 7. `enumerate`, tuples

A very common occurence is to loop over a list and you want to keep track of both the item and its index. The ugly way to do this is:

```python
students = ["Yana","John","Andrew","Tara"]
for i in range( len(students) ):
    print(i, students[i])
>>>> 0 Yana
>>>> 1 John
>>>> 2 Andrew
>>>> 3 Tara
```

The much cleaner way to do this is to use `enumerate()`.

```python
students = ["Yana","John","Andrew","Tara"]
for i, person in enumerate(students):
    print(i, person)
>>>> 0 Yana
>>>> 1 John
>>>> 2 Andrew
>>>> 3 Tara
```

A tuple is similar to a list as it keeps ordered information. Tuples are used in slightly different contexts. For us the distinction won't be too important, and we will often stick to lists. Here's what the Python documentation says about it:

> Though tuples may seem similar to lists, they are often used in different situations and for different purposes. Tuples are immutable, and usually contain a heterogeneous sequence of elements that are accessed via unpacking (see later in this section) or indexing (or even by attribute in the case of namedtuples). Lists are mutable, and their elements are usually homogeneous and are accessed by iterating over the list.

```python
student_info = [("Yana", 87), ("John", 92), ("Andrew", 314), ("Tara", -2)]
for data in student_info:
    print student_info[data][1]
```

### Technical warning

Lists behave somewhat strangely with variable assignment. Python does not copy a list when it is assigned as a variable, it merely points to the original list. This can have unintended consequences!

```python
students = ["Yana","John","Andrew","Tara"]
in_class = students

in_class.remove("Tara") # Tara leaves the room
print(students)
>>>> ['Yana', 'John', 'Andrew']
```

## Project 1. Project Euler 1 (part 2)

Last week you did the `if` statement needed for the first Project Euler problem. Now you can complete it by combining it with a `for` loop.

## Project 2. Project Euler Problem 16.

Python can make short work of [Problem 16](https://projecteuler.net/problem=16) since it is perfectly happpy computing large powers of 2. Solve the problem, submit your Solution to Project Euler, and save your code on Github.
