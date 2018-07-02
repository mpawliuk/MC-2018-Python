# 1-2. Strings and Printing

In this lesson we'll learn the basics of handling strings.

## Outline

1. Escaping characters
2. Index and Truncating
3. String methods (`.upper()`, `.lower()`, `.split()`, `len()`, `.replace()`, `.find()`)
4. Basic string concatination (`+`)
5. String replacement formatting (`%`)
6. Input from the user (`input()`, `raw_input()`)

Project: Madlibs.

## 1. Escaping characters

When using strings, some characters mess with the code. Things like `'`, `"` and `\` get used in English sentences, but to include them in strings we need to **escape** the character with a backslash `\`.

### Exercise

Fix the following code by escaping the problem characters.

```python
greeting = 'Let's make math today!'
response = "My friend said, "that's a good idea."."
hashtag = "#YOLO"
print(greeting, response,hashtag)
```

## 2. Index and Truncating

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
### Exercise



## 3. String methods (`.upper()`, `.lower()`, `.split()`, `len()`, `.replace()`, `.find()`)

## 4. Basic string concatination (`+`)

## 5. String replacement formatting (`%`)

## 6. Input from the user (`input()`, `raw_input()`)

## Project: Madlibs.

In this project you will make a Madlib. A Madlib is a word game where one player is prompted to give an ordered list of words (usually nouns, adjectives, verbs) without seeing the rest of the text. Once all the words have been chosen, they are inserted into the text, with silly results.

* A noun is a person, place or thing. e.g. Mike, classroom, bicycle.
* An adjective is a describing word. Fast, smart, slimy.
* A verb is an action word. Jump, slurp, roll.
* An adverb modifies a verb or an adjective. Quickly, well, smartly.

For example, choose a `noun` and an `adjective`. Now place them in this text:

> I was late for my Python class today because I forgot my [---*noun*---] in my room. It got very messy and [---adjective---]

Your task is to use string replacement and user input to create a madlib game. You can use [this math-themed Madlib](https://www.woojr.com/wp-content/uploads/2017/07/math-madlibs.jpg) as inspiration, or use it directly. After you've made it, upload it to the common folder for others to play.
