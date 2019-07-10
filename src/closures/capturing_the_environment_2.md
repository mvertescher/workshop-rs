# Capturing the Environment

When a closure captures a value from its environment it uses memory to store
the values for use in the closure body.

As a result, closures incur some memory overhead while functions, which never
capture their environments, do not.
