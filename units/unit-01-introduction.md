# Unit 1 — Introduction and Fundamental Concepts

## Goals

After this unit, you can explain what a program is, describe an algorithm, run a Python script, use basic input and output, and investigate a simple error systematically.

## 1. What is programming?

A **program** is a set of instructions a computer can execute. **Programming** is the process of designing those instructions, expressing them in a language, and checking that they solve the intended problem. Computers follow instructions precisely; they do not fill in missing steps the way a person might.

An **algorithm** is a finite, ordered set of steps for solving a problem. For example, to find the average of three quiz scores: collect the scores, add them, divide by three, and show the result. A good algorithm is clear, has a stopping point, and works for the cases it claims to handle.

A programmer's usual cycle is:

1. Understand the problem and identify inputs and expected outputs.
2. Plan the steps (plain language or pseudocode is fine).
3. Implement a small part.
4. Run it and compare actual output with expected output.
5. Fix, test again, and explain the result.

## 2. Your first Python program

Create `hello.py`:

```python
print("Hello, world!")
print("I am learning Python.")
```

`print` displays information. Text inside quotation marks is a **string**. Parentheses provide the argument to the function. Python runs statements in order, from top to bottom.

Run the file. If you see a syntax error, check quotation marks, parentheses, and spelling. Python distinguishes uppercase and lowercase: `print` is not the same as `Print`.

## 3. Values, expressions, and types

A **value** is a piece of data. Examples include `12`, `3.5`, `"Ada"`, and `True`. An **expression** is code Python evaluates to produce a value: `2 + 3` produces `5`.

```python
print(2 + 3)          # 5
print("Py" + "thon")  # Python
print(2 * 3)          # 6
```

The `#` symbol starts a comment; Python ignores the rest of that line. Comments should explain intent, not repeat obvious code.

## 4. Input and output

`input()` displays a prompt and returns what the user typed as text:

```python
name = input("What is your name? ")
print("Welcome,", name)
```

The `=` here stores a value in a name; it is called **assignment**. The name `name` refers to the entered string. Input can be surprising: even if a user types `42`, `input()` returns `"42"`, not the number `42`.

Convert text to a number when arithmetic is needed:

```python
age_text = input("How old are you? ")
age = int(age_text)
print("Next year you will be", age + 1)
```

`int()` converts valid integer text. If the user types something like `many`, conversion fails. We will learn to handle such cases later.

## 5. Trace a program

Tracing means following each statement and recording the values as Python executes it.

```python
distance = 10
minutes = 2
speed = distance / minutes
print(speed)
```

After line one, `distance` is `10`; after line two, `minutes` is `2`; then `speed` becomes `5.0`. Predict the output before running it. Tracing is useful when output differs from what you expected.

## Practice

1. Write a script that prints your name and one reason you want to learn programming.
2. Ask for two whole numbers, convert them with `int()`, and print their sum.
3. Write plain-language steps for deciding whether a given number of minutes is enough time to walk a route (choose and state your own assumptions).
4. Trace `a = 4; b = a + 3; a = 1; print(b, a)`. What prints, and why?

## Suggested answers

1. Use two `print()` calls with your own text.
2. Example: `first = int(input("First number: "))`, then repeat for `second`, and print `first + second`.
3. One valid plan: ask for route duration and available minutes; if duration is no greater than available time, say there is enough time; otherwise say there is not. The comparison itself is introduced in Unit 3.
4. `7 1`: `b` receives the value `7` when that assignment runs. Changing `a` later does not retroactively change `b`.

## Check your understanding

- What is the difference between an algorithm and a program?
- What type of value does `input()` return?
- In what order does Python execute ordinary statements in a script?
- What information can a traceback provide?

**Next:** Unit 2 introduces names, types, expressions, statements, and calling functions.
