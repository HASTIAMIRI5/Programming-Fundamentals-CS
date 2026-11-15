# Unit 4 — Functions and Return Values

## Goals

Define and call functions, use parameters and arguments, return values, distinguish `return` from `print`, and use local variables to break problems into manageable pieces.

## 1. Define, then call

A function definition describes an operation. It does not run its body until the function is called.

```python
def greet(name):
    message = f"Hello, {name}!"
    return message

welcome = greet("Ari")
print(welcome)
```

`name` is a **parameter**: a local name for an input. `"Ari"` is the **argument** supplied in the call. `return` sends a result back to the caller and ends that function call.

## 2. Return is not print

`print(value)` displays something for a person. `return value` gives a result back to code so it can be stored, combined, or tested.

```python
def area(width, height):
    return width * height

room_area = area(4, 5)
print(room_area + 2)
```

A function that reaches its end without a `return` statement returns `None`. Avoid relying on output from a function when another part of your program needs to use the calculated result.

## 3. Decompose a problem

Suppose a program calculates a sales total after a discount and tax. Separate the calculations into named operations:

```python
def discounted_price(price, discount_rate):
    return price * (1 - discount_rate)

def add_tax(price, tax_rate):
    return price * (1 + tax_rate)

subtotal = discounted_price(100, 0.10)
total = add_tax(subtotal, 0.08)
print(f"Total: ${total:.2f}")
```

The rate is a decimal fraction: `0.10` means 10%. Decomposition makes each part easier to test and change.

## 4. Scope and design

A parameter and variables created inside a function are normally **local** to that call. They are not automatically available outside it. Prefer passing inputs as parameters and returning results rather than changing global variables; this makes behavior easier to understand.

A good function generally has a clear name, a focused job, explicit inputs, and a useful result. Validate assumptions when appropriate:

```python
def average(total, count):
    if count <= 0:
        raise ValueError("count must be positive")
    return total / count
```

This introduces an exception: a signal that the function cannot complete its job under the given conditions. Exception handling is covered in Unit 8.

## 5. Test a function

Call it with typical values and boundary cases. For `area`, try positive dimensions and zero. For a discount function, test a 0% discount and the maximum discount your rules allow. If a function promises a number, verify it returns a number rather than merely printing one.

## Practice

1. Write `celsius_to_fahrenheit(celsius)` using `F = C * 9 / 5 + 32` and return the result.
2. Write `is_multiple(number, divisor)` that returns a Boolean. Decide what should happen when `divisor` is zero.
3. Write `total_with_tip(bill, tip_rate)` and return the total.
4. In your own words, explain why a function that prints `42` is different from one that returns `42`.

## Suggested answers

1. `def celsius_to_fahrenheit(celsius): return celsius * 9 / 5 + 32`.
2. If `divisor == 0`, raise `ValueError`; otherwise return `number % divisor == 0`.
3. `def total_with_tip(bill, tip_rate): return bill * (1 + tip_rate)`.
4. Printing shows a value to the user; returning makes it available to the caller for further computation.

## Check your understanding

What is the difference between a parameter and an argument? When does a function body run? What value is returned if execution reaches the end without `return`?

**Next:** Unit 5 repeats work with loops and processes text with strings.
