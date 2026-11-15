# Unit 6 — Lists

## Goals

Create lists, access and update elements, traverse a list, add and remove items, and choose a list when you need an ordered collection that can change.

## 1. Create and access lists

A list stores an ordered collection, which may contain values of the same or different types:

```python
scores = [82, 95, 71]
empty_list = []
print(scores[0])   # 82
print(scores[-1])  # 71
print(len(scores))
```

Indexes start at 0. Accessing an index that does not exist raises `IndexError`. Check the length or iterate over the list when the index is not known.

## 2. Lists are mutable

Unlike strings, lists can be changed after they are created:

```python
scores[1] = 97
scores.append(88)
scores.insert(0, 76)
print(scores)
```

Common operations: `append(item)` adds at the end; `insert(index, item)` inserts; `remove(value)` removes the first matching value; `pop()` removes and returns the last item (or `pop(index)` removes at an index). `sort()` rearranges a list in place. Check that the item exists before removing it if absence is possible.

## 3. Traverse and calculate

```python
scores = [82, 95, 71]
total = 0
for score in scores:
    total += score
average = total / len(scores)
print(average)
```

This assumes the list is not empty. A safe function should define what an empty list means: return `None`, return a special value, or raise an informative exception.

If you need both the index and item, use `enumerate`:

```python
for position, score in enumerate(scores):
    print(position, score)
```

## 4. Slices and copying

A slice selects a portion: `scores[1:3]` includes indexes 1 and 2. Slices make a new list. Assignment such as `other = scores` does not copy the list; it makes another name for the same object. A shallow copy can be made with `scores.copy()` or `scores[:]`.

```python
original = [1, 2]
reference = original
reference.append(3)
print(original)  # [1, 2, 3]
```

This aliasing behavior matters when passing mutable lists to functions.

## 5. Build a filtered list

```python
numbers = [3, 8, 11, 14, 20]
evens = []
for number in numbers:
    if number % 2 == 0:
        evens.append(number)
print(evens)  # [8, 14, 20]
```

A list comprehension can express the same transformation compactly: `evens = [number for number in numbers if number % 2 == 0]`. Learn the loop version first; use a comprehension when it stays readable.

## Practice

1. Ask for five numbers, store them in a list, and print the largest and smallest.
2. Write `count_matches(items, target)` that returns how many times `target` occurs.
3. Given a list of words, build and print a new list containing only words longer than five characters.
4. Explain why `b = a` does not make an independent list copy.

## Suggested answers

1. Start `numbers = []`; repeat five times and append `float(input(...))`; then use `max(numbers)` and `min(numbers)`.
2. Initialize a count to zero, traverse the list, increment when an item equals `target`, and return the count. `items.count(target)` is built in, but writing the loop demonstrates the algorithm.
3. Traverse the words and append each word when `len(word) > 5`, or use a comprehension.
4. Both names refer to the same mutable list, so a change through either name is visible through the other.

## Check your understanding

What is the first list index? What does `append` do? How do list and string mutability differ?

**Next:** Unit 7 represents records with dictionaries and fixed groups with tuples.
