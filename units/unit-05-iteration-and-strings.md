# Unit 5 — Iteration and Strings

## Goals

Repeat instructions with `for` and `while`, avoid infinite loops, traverse strings, and use common string operations and methods.

## 1. `for` loops

Use `for` when iterating over items or a known sequence of numbers:

```python
for number in range(1, 5):
    print(number)
```

This prints 1, 2, 3, 4. The stop value is excluded. `range(start, stop, step)` can specify a starting value and step; `range(5)` produces 0 through 4.

A string is a sequence of characters:

```python
for character in "code":
    print(character)
```

## 2. `while` loops

Use `while` when repetition depends on a condition that may change:

```python
answer = ""
while answer != "yes":
    answer = input("Type yes to continue: ").strip().lower()
print("Continuing")
```

A loop needs a path that eventually makes its condition false. Otherwise it can run forever. The `.strip()` method removes surrounding whitespace; `.lower()` normalizes letters to lowercase.

## 3. Accumulate a result

An **accumulator** collects a result as a loop runs:

```python
total = 0
for value in range(1, 6):
    total = total + value
print(total)  # 15
```

Before the loop, decide the accumulator's initial value and how it changes on each iteration. For a count, start at `0`; for a product, start at `1`.

## 4. Strings

Strings are ordered sequences of characters. `len(text)` gives the character count. Indexing starts at 0; negative indexes count from the end. Slices select part of a string, with the ending index excluded:

```python
word = "Python"
print(word[0])     # P
print(word[-1])    # n
print(word[1:4])   # yth
```

Strings are immutable: methods return new strings rather than changing the original.

```python
text = "  Hello, World!  "
clean = text.strip().lower()
print(clean)  # hello, world!
```

Useful methods include `.lower()`, `.upper()`, `.strip()`, `.replace(old, new)`, `.find(substring)`, and `.split(separator)`. The `in` operator checks for a substring: `"Py" in "Python"` is `True`.

## 5. Combining iteration and strings

```python
text = input("Enter text: ")
vowels = 0
for character in text.lower():
    if character in "aeiou":
        vowels += 1
print(f"Vowels: {vowels}")
```

The `+=` operator adds to the current value and assigns it back. This example counts English vowel letters; it is not a complete linguistic definition of vowels.

## Practice

1. Use a loop to print multiples of 3 from 3 through 30.
2. Ask for a word and print its characters in reverse order. (Hint: `word[::-1]` returns a reversed copy.)
3. Count how many digits (`0` through `9`) occur in a line of text.
4. Keep asking for a non-empty name; trim surrounding spaces before accepting it.

## Suggested answers

1. `for number in range(3, 31, 3): print(number)` with the body indented.
2. `word = input("Word: ")`; `print(word[::-1])`.
3. Traverse each character and increment a counter when `character in "0123456789"`.
4. Set `name = input("Name: ").strip()` before the loop; while not `name`, ask again and strip again.

## Check your understanding

What is excluded from a `range` stop value? What makes a `while` loop terminate? Why does `text.lower()` not change `text` itself?

**Next:** Unit 6 stores collections of values in lists.
