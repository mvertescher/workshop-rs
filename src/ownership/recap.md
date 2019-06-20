# Recap

__Ownership__

- Each _value_ in Rust has a _variable_ that's called its _owner_.
- There can only be one owner for a value at a time.
- When the owner goes out of scope, the value will be dropped.

__References__

- At any given time, you can either have one mutable reference or any number of
  immutable references.
- References must always be valid.
