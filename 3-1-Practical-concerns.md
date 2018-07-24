## 3-1. Computational thinking and practical concerns

1. Making a plan. (Test cases, pass)
2. Brute force algorithms.
3. Runtime and memory differences (for loops, comprehension, lists vs iterators)
4. Debug tools (printing, assert)
5. Python 2 vs Python 3.

**Project**: Project Euler Problems 81, 82, 83 (part 1)

## 1. Making a plan. (Test cases, pass)

When solving a problem, one of your first steps should be to make a plan. Before you start coding you should understand what you want your code to do, and how you want it to go.

1. Make a plan.
2. Draw a flow chart.
3. Describe in words what you want your code to do.

```python
# I want a function that returns the two largest elements of a list.
# Strategy 1: Sort the list, then use list indexing to grab list[-2], list[-1] to grab the items.
# Strategy 2: Use the max function to find the largest item, then remove it, and use max again.
# Strategy 3: Use two variables to keep track of the current largest and second largest items. Loop through the list updated the variables as I go.
```

It can be helpful to use simplified data or cases when checking that the code works as intended. Use a smaller data set before you go to the full data set.

### Exercise

The following code is not running as expected. Use a smaller list of `names` to help identify the problem.

```python
names = ["Yana","John","Andrew","Tara","George","Maxim","Devanshu","Max","Vishnu","Adrien","Audrey","Sophia","Joy","Lizette","Oskar","Will","Ethan"]

a_count = 0
for name in names:
  if name[0] == 'a':
    a_count += 1
print(a_count)
```

## 2. Brute force algorithms.

A **brute force** algorithm is one that runs through all possible cases, without using any observations to help speed up the runtime. These can be helpful when working with small cases, but should be avoided for larger data. Use modules and packages when possible instead of rewriting code; it's likely that their code is more efficient.

```python
# Brute Force Multiplicative inverse

def brute_mult_inverse(a,n):
  """Solve ax = 1 mod n using brute force."""
  for x in range(n):
    if a*x%n == 1:
      return x
  return None

print( brute_mult_inverse(94, 97) )
```

## 3. Runtime and memory differences (for loops, comprehension, lists vs iterators)

Remember that nested `for` loops quickly add up (really... multiply up). So using brute force can get out of hand fast. In general, Python can handle about 1 million arithmetic operations per second on your usual desktop computer.

Use list comprehension when possible, as long as it doesn't impact readability.

```python
comp_squares = [x**2 for x in range(10)]

squares = []
for x in range(10):
  squares.append(10)
```

We've skipped over the difference between `list`s and iterators. Python stores a `list` with all of its information at once. This can use a lot of memory! Python uses an iterator to increment one-at-a-time through a collection. It doesn't store the whole amount of information all at once, it only keeps track of one thing at a time. This can have notable differences in runtime.

This is why you can't just `print( range(10) )`, since `range(10)` is an iterator. You can however loop through iterators.

```python
import time
start = time.time()

n = 10000000

# list
for i in list(range(n)):
  pass
print( time.time() - start )
>>>> 2.247755527496338

# Iterators
start = time.time()
for i in range(n):
  pass
print( time.time() - start )
>>>> 0.9638926982879639
```

### Exercise

Use list comprehension and `sum` to write Ursula's code in one line.

```python
total = 0
for i in range(100):
  total += i
print(total)
```

## 4. Debug tools (printing, assert)

Printing variables is a slow, but helpful way of finding misbehaving code.

```python
names = ["Yana","John","Andrew","Tara","George","Maxim","Devanshu","Max","Vishnu","Adrien","Audrey","Sophia","Joy","Lizette","Oskar","Will","Ethan"]

a_count = 0
for name in names:
  print( name, name[0] == 'a', name[0])
  if name[0] == 'a':
    a_count += 1
print(a_count)
```

Another useful tool is `assert` which acts as a gatekeeper by checking that a statement is true. For example `assert(x != 0)` would check to see that x is nonzero, and would throw an error if found.

```python
for p in range(5):
  for q in range(5):
    assert 4-q != 0, "{},{}".format(p,q) 
    print(p/(4-q))
```

## 5. Python 2 vs Python 3.

There are some differences between Python 2 and 3 that you should be aware of.

1. Python 2 does not need brackets for `print`, but Python 3 does.
2. Python 2 treats `range(n)` as a list, but Python 3 treats it like an iterator.
3. Python 2 treats `a/b` as integer division, wheras Python 3 treats `a/b` as float division.
4. Python 2 lets you call variables you defined for a for loop outside of that loop, but Python 3 does not. (That's a good change!)

```python
for i in range(5):
  print (i**2)
# This works in Python 2, but not in Python 3
print i
```

## Project 1. Project Euler Problem 34

Solve [Project Euler Problem 34](https://projecteuler.net/problem=34) which has do with factorials. First make a plan, and make some simplifying mathematical assumptions.

## Project 2. 81, 82, 83 (part 1)

These problems all build on each other and involve finding the shortest path through a grid. Make a plan for finding the answer.

1. Understand the math involved.
2. How do you measure what you're looking for? Must you use brute force, or is there another option?
3. How does this problem work in the 2x3 case, or the 3x3 case?
4. What will your code loop over, and in what order?
5. What will your code do at each stage? Will that operation require a "helper function"?
