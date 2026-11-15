# Unit 3 — Conditionals and Recursion

## Goals

Compare values, combine Boolean expressions, choose among branches with `if`/`elif`/`else`, and understand the base case and recursive step of a recursive function.

## 1. Comparisons and Boolean logic

Comparisons produce `True` or `False`: `==`, `!=`, `<`, `<=`, `>`, and `>=`. Use `==` to compare values; a single `=` assigns a value.

```python
age = int(input("Age: "))
print(age >= 18)
```

Boolean operators combine conditions: `and` requires both conditions to be true; `or` requires at least one; `not` reverses a truth value.

```python
has_ticket = True
is_adult = False
print(has_ticket and is_adult)  # False
```

Use parentheses to make complex conditions clear. Python evaluates `and` and `or` with short-circuit behavior: it may not evaluate the second part when the first part already determines the result.

## 2. Branching

```python
temperature = float(input("Temperature in C: "))
if temperature < 0:
    print("Below freezing")
elif temperature < 20:
    print("Cool")
else:
    print("Warm")
```

Only the first matching branch runs. `elif` means “otherwise, if.” Indentation defines each block. Notice that the second condition only needs `temperature < 20`: reaching it already means the first condition was false.

A practical example:

```python
number = int(input("Enter an integer: "))
if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

## 3. Recursion: a function that solves a smaller version

A recursive function calls itself. Every sound recursive design needs:

1. A **base case** that returns without another recursive call.
2. A **recursive case** that makes progress toward the base case.

For example, the sum of positive integers from 1 to `n` can be defined as `n + sum_to(n - 1)`, with `sum_to(1) = 1`:

```python
def sum_to(n):
    if n <= 1:
        return n
    return n + sum_to(n - 1)

print(sum_to(4))  # 10
```

Trace `sum_to(4)`: it becomes `4 + sum_to(3)`, then `4 + 3 + sum_to(2)`, then `4 + 3 + 2 + sum_to(1)`. The base case returns `1`, and the calls finish in reverse order. For `n <= 0`, this example returns `n`; if the intended domain is positive integers only, validate that domain explicitly.

Recursion can be elegant for naturally nested problems, but it uses call-stack space and Python limits recursion depth. For simple counting tasks, loops are often clearer.

## Practice

1. Ask for a number and report whether it is positive, negative, or zero.
2. Ask for a score from 0 to 100 and assign a letter-grade band using your own stated boundaries. Handle out-of-range values.
3. Write `countdown(n)` recursively so it prints `n` down to `1`, then `"Go!"`. Identify its base case and explain how each call progresses.
4. Trace `sum_to(3)` by listing each call and return.

## Suggested answers

1. Use `if number > 0`, `elif number < 0`, and `else`.
2. First reject values below 0 or above 100. Then test bands from highest to lowest, for example `>= 90`, `>= 80`, and so on. The exact bands are a policy choice; state them.
3. One solution: `def countdown(n):\n    if n <= 0:\n        print("Go!")\n    else:\n        print(n)\n        countdown(n - 1)`. The base case is `n <= 0`; each call reduces `n` by one.
4. Calls: `sum_to(3) -> 3 + sum_to(2) -> 3 + 2 + sum_to(1)`. Returns: `sum_to(1)=1`, `sum_to(2)=3`, `sum_to(3)=6`.

## Check your understanding

Why is `if x = 3:` invalid? What happens if a recursive function never reaches its base case? Why might a loop be preferable to recursion?

**Next:** Unit 4 creates reusable functions that return results.
