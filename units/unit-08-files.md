# Unit 8 — Files

## Goals

Read and write text files using context managers, understand file paths and modes, and handle expected input/output errors.

## 1. Why files?

Values stored in variables disappear when a program ends. A file can preserve information between runs. Text files are useful for notes, settings, and simple datasets. A file path identifies where the file is located; relative paths are resolved from the program's current working directory.

## 2. Read text safely

Use `with open(...)` so Python closes the file automatically, even if an error occurs:

```python
with open("notes.txt", "r", encoding="utf-8") as file:
    contents = file.read()

print(contents)
```

Mode `"r"` means read. `encoding="utf-8"` supports a broad range of text. To read line by line:

```python
with open("notes.txt", "r", encoding="utf-8") as file:
    for line in file:
        print(line.rstrip())
```

Each line usually includes a newline character; `.rstrip()` removes trailing whitespace. `.strip()` removes whitespace at both ends, so use the one that matches your goal.

## 3. Write and append

```python
with open("journal.txt", "w", encoding="utf-8") as file:
    file.write("Today I learned about files.\n")
```

Mode `"w"` creates a file or replaces its existing contents—be careful. Mode `"a"` appends to the end. `write()` does not add a newline automatically, so include `\n` when needed.

## 4. Handle expected errors

A file may not exist, or the program may not have permission to access it. Catch a specific exception when you can respond usefully:

```python
try:
    with open("notes.txt", "r", encoding="utf-8") as file:
        contents = file.read()
except FileNotFoundError:
    print("notes.txt was not found. Create it first.")
else:
    print(contents)
```

`try` contains the operation that may fail; `except` handles the named failure; `else` runs when no exception was raised. Avoid broad `except:` clauses that hide programming errors.

## 5. Small persistence exercise

A simple score log can append one score per run:

```python
score = int(input("Score: "))
with open("scores.txt", "a", encoding="utf-8") as file:
    file.write(f"{score}\n")
```

Reading these values later requires converting each line from text to an integer. Consider how the program should respond if a line is blank or malformed.

## Practice

1. Create a text file with three lines. Write a program to display each line without extra blank lines.
2. Ask the user for a note and append it to `journal.txt` with a newline.
3. Read integer scores from `scores.txt` and calculate their average. Define behavior for a missing file, invalid line, or empty file.
4. Explain the difference between `"w"` and `"a"` modes.

## Suggested answers

1. Open in read mode with UTF-8 and loop through lines, printing `line.rstrip()`.
2. Open with mode `"a"`, then write the input plus `"\n"`.
3. Read lines in a `try` block, convert non-empty lines with `int`, and calculate only if the resulting list is non-empty. Catch `FileNotFoundError` and decide whether invalid data should be skipped or reported; document that choice.
4. `"w"` replaces existing contents; `"a"` adds to the end while preserving existing contents.

## Check your understanding

Why use a `with` block? Why specify an encoding? What is the risk of opening an important file in write mode?

**Next:** Unit 9 reviews the course and presents an integrated capstone assessment.
