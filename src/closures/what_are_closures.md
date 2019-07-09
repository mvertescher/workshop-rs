# What _Are_ Closures?

In general, closures are a record storing a function together with an environment.

Unlike a function, a closure allows access to _captured variables_ through the
closure's copies of their values or references.

Here's a short closure example in Python:

```py
def f(x):
    def g(y):
        return x + y  # `x` is captued from the outer scope
    return g  # Return a closure

def h(x):
    return lambda y: x + y  # Return a closure

# Assigning specific closures to variables.
a = f(1)
b = h(1)

# Using the closures stored in variables.
assert a(5) == 6
assert b(5) == 6

# Using closures without binding them to variables first.
assert f(1)(5) == 6  # f(1) is the closure.
assert h(1)(5) == 6  # h(1) is the closure.
```
