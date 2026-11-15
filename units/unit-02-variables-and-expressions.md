# Unit 2 — Variables, Expressions, Statements, and Functions

## Goals

Use variables to name values, distinguish common types, build expressions with operators, and recognize the difference between a function call and a function definition.

## 1. Variables and assignment

A variable is a name bound to a value. Assignment evaluates the right-hand side first, then stores that result under the name on the left:

```python
price = 12.50
quantity = 3
total = price * quantity
print(total)  # 37.5
```

Names may contain letters, digits, and underscores, but cannot begin with a digit. Use meaningful `snake_case` names such as `item_count`. A later assignment replaces the value associated with a name:

```python
score = 8
score = score + 2
```

This is not a mathematical equation. Python evaluates the old `score + 2`, then assigns the result back to `score`.

## 2. Common data types

- `int`: whole numbers, such as `-4` and `20`.
- `float`: numbers with a fractional part, such as `2.5`.
- `str`: text, such as `"hello"`.
- `bool`: `True` or `False`.

Use `type(value)` to inspect a value's type. Convert deliberately: `int("15")` gives `15`, `float("2.5")` gives `2.5`, and `str(15)` gives `"15"`. Not every string can be converted to a number.

## 3. Operators and expressions

Arithmetic operators include `+`, `-`, `*`, `/`, `//` (floor division), `%` (remainder), and `**` (power). Parentheses make intended order explicit.

```python
print(17 / 5)   # 3.4
print(17 // 5)  # 3
print(17 % 5)   # 2
print(2 ** 3)   # 8
```

Strings can be joined with `+` and repeated with `*`: `"ha" * 3` gives `"hahaha"`. Adding a string and a number directly is a type error; convert the number or use an f-string:

```python
name = "Sam"
points = 12
print(f"{name} earned {points} points.")
```

## 4. Statements and function calls

An **expression** produces a value. A **statement** performs an action, such as assigning a name or displaying output. A **function** is a named operation that can accept inputs (arguments) and may produce a result.

```python
length = len("Python")  # function call; result is 6
rounded = round(3.14159, 2)
print(rounded)           # 3.14
```

`len` and `round` are built-in functions. In `len("Python")`, the text is an argument. Function calls can be nested, but simpler intermediate names often make code easier to read.

## 5. A useful numeric program

```python
minutes = int(input("Minutes studied: "))
hours = minutes / 60
print(f"That is {hours} hours.")
```

Test with `0`, a typical positive number, and a negative number. Whether negative minutes should be accepted is a design decision; programs should define what inputs make sense.

## Practice

1. Ask for a rectangle's width and height, convert them to floats, and print its area and perimeter.
2. Given `seconds = 367`, calculate whole minutes and remaining seconds using `//` and `%`.
3. Predict the values of `x` and `y`: `x = 5; y = x * 2; x = x + 1`.
4. Explain the difference between `print(4 + 5)` and `answer = 4 + 5`.

## Suggested answers

1. `width = float(input(...))`, `height = float(input(...))`; area is `width * height`, perimeter is `2 * (width + height)`.
2. `minutes = 367 // 60` gives `6`; `remaining = 367 % 60` gives `7`.
3. `x` is `6`, `y` is `10`. `y` stores the value calculated before `x` changes.
4. The first displays the result; the second stores it in a name and produces no output by itself.

## Check your understanding

What does `%` calculate? Why does `input()` often need conversion? What does a function call provide that a variable assignment does not?

**Next:** Unit 3 uses Boolean expressions to choose between actions and introduces recursion.
