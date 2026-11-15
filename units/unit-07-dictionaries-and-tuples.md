# Unit 7 — Dictionaries and Tuples

## Goals

Store and retrieve values by key in dictionaries, use tuples for fixed grouped values, and choose a data structure that matches the information and operations a program needs.

## 1. Dictionaries: key-value associations

A dictionary maps unique keys to values. Use it when you need to look up a value by a meaningful label rather than a numeric position.

```python
person = {"name": "Mina", "age": 21}
print(person["name"])
person["age"] = 22
person["city"] = "Lima"
```

Keys are commonly strings or numbers and must be hashable. Values can be many types, including lists or other dictionaries. Accessing a missing key with square brackets raises `KeyError`.

Use `get` when a key may be absent:

```python
email = person.get("email", "not provided")
```

The second argument is a default value. `person.keys()`, `.values()`, and `.items()` provide views for iteration.

## 2. Count with a dictionary

```python
text = "to be or not to be"
counts = {}
for word in text.split():
    counts[word] = counts.get(word, 0) + 1
print(counts)
```

The pattern `counts.get(key, 0) + 1` means “use zero if we have not seen this key; then add one.” Dictionaries are also useful for settings, inventories, and looking up contact details.

## 3. Tuples: ordered groups

A tuple is an ordered, immutable sequence:

```python
point = (4, 7)
x, y = point
print(x, y)
```

Tuples can represent a fixed record, such as a coordinate or an RGB color. A one-item tuple needs a trailing comma: `(5,)`; `(5)` is just the integer `5`. Immutability means tuple positions cannot be reassigned, though a tuple containing a mutable object does not make that contained object immutable.

## 4. Choosing a structure

- Use a **list** for an ordered collection that changes or is traversed by position.
- Use a **dictionary** for lookup by key or labeled fields that may be added or updated.
- Use a **tuple** for a small, fixed ordered group of values.

A list of dictionaries can represent several records:

```python
students = [
    {"name": "Mina", "score": 91},
    {"name": "Omar", "score": 84},
]
for student in students:
    print(student["name"], student["score"])
```

As programs grow, data classes may be useful, but these core structures are enough for many beginner projects.

## Practice

1. Create a dictionary mapping three product names to prices. Print the price of one product using its key.
2. Count the occurrences of each character in a string, ignoring spaces and letter case.
3. Represent a 2D coordinate as a tuple and unpack it into `x` and `y`.
4. You need to store tasks in their order of completion and look up a user's phone number by username. Which structures fit each job, and why?

## Suggested answers

1. Example: `prices = {"tea": 2.5, "bread": 3.0, "rice": 4.25}`; then `print(prices["tea"])`.
2. Normalize with `.lower()`, loop through characters, skip spaces, and increment `counts[character] = counts.get(character, 0) + 1`.
3. `coordinate = (3, 8)`; `x, y = coordinate`.
4. Use a list for the ordered tasks and a dictionary mapping username to phone number for direct lookup.

## Check your understanding

What does `dict.get` help avoid? How is a tuple different from a list? Why is a dictionary useful for counting?

**Next:** Unit 8 reads and writes files so data can survive after a program ends.
