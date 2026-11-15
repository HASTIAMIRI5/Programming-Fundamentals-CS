# Unit 9 — Course Review and Final Exam

## Review map

A useful program brings the course topics together:

- **Values and variables:** represent the information your problem needs.
- **Expressions and types:** calculate and transform values deliberately.
- **Conditionals:** choose an action based on a condition.
- **Loops:** repeat an action over a sequence or until a condition changes.
- **Functions:** divide a solution into focused, testable operations.
- **Lists, dictionaries, and tuples:** organize related data appropriately.
- **Files:** load and save information beyond one run.
- **Testing:** compare actual behavior with requirements, including unusual inputs.

## A repeatable problem-solving method

1. Restate the problem. What exactly should the program do?
2. List inputs, outputs, and assumptions. What can be invalid or missing?
3. Break the work into small steps. Identify repeated operations that could be functions.
4. Write a small version and test it early.
5. Test normal cases, boundary cases, and invalid cases.
6. Read errors, trace values, fix one issue at a time, and retest.
7. Clean up names and structure; explain any assumptions in comments or documentation.

## Capstone: Personal reading log

Build a command-line reading log. Store records in a UTF-8 text file. Each record should contain a book title, author, and page count. The program should provide a simple menu to:

1. Add a book.
2. Show all saved books.
3. Show the total number of pages recorded.
4. Quit.

### Requirements and planning hints

- Use functions such as `show_menu`, `add_book`, `read_books`, and `main` to organize the work.
- Use a loop to keep showing the menu until the user quits.
- Use conditionals to handle each menu choice and report unknown choices.
- Store each book as a dictionary or tuple while the program is running; a list is a suitable collection of records.
- Use a file format that handles titles containing punctuation. A beginner-friendly option is one JSON record per line using Python's standard `json` module; alternatively, specify a simpler format and its limitations.
- Handle a file that has not been created yet. Validate that page count is a non-negative integer.
- Test an empty file, one record, several records, a missing file, and invalid menu/page input.

A useful first milestone is implementing and testing `read_books()` before building the menu. Keep the data-reading and data-writing functions separate from user interaction. This makes the program easier to test and modify.

## Final review questions

1. What is the difference between assignment (`=`) and equality comparison (`==`)?
2. What does a function return if it has no explicit `return`?
3. What makes a `while` loop infinite, and how can you prevent that?
4. If `items = ["a", "b", "c"]`, what is `items[1]`? What does `items[1:3]` contain?
5. When would you use a dictionary instead of a list?
6. Why is `with open(...)` preferable to opening a file without a context manager?
7. Describe a base case and a recursive case.
8. Name three tests you would use for a function that converts a temperature.

### Answer guide

1. `=` assigns; `==` compares values.
2. `None`.
3. The loop condition never becomes false; ensure the loop body updates relevant state and test the stopping condition.
4. `"b"`; the slice is `["b", "c"]` because the ending index is excluded.
5. When values should be looked up by a meaningful key rather than position.
6. It closes the file automatically, including when an exception occurs.
7. The base case stops recursion; the recursive case makes progress toward that case.
8. A typical value, a boundary such as freezing point, and a negative value; expected outcomes should be calculated independently.

## Final exam preparation checklist

- Can you explain your code line by line without relying on memorized phrases?
- Can you write a small function from a plain-language requirement?
- Can you trace a loop and predict its final state?
- Can you identify an off-by-one error in a `range` or slice?
- Can you select a list, dictionary, or tuple and justify the choice?
- Can you read and write a file while handling likely errors?
- Have you tested normal, edge, and invalid cases?

## Self-assessment

Rate each course outcome as **confident**, **developing**, or **needs practice**. For every “needs practice,” return to the corresponding unit, write a small example from scratch, and explain the result to someone else. The goal is not merely to memorize syntax; it is to be able to reason about and test a solution.
