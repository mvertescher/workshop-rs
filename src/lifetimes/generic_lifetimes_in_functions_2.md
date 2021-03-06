# Generic Lifetimes in Functions

Let's implement the longest function:

```rust,ignore
fn longest(x: &str, y: &str) -> &str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

Interestingly, this does not compile and returns this error message:

```plaintext
error[E0106]: missing lifetime specifier
 --> src/main.rs:4:33
  |
4 | fn longest(x: &str, y: &str) -> &str {
  |                                 ^ expected lifetime parameter
  |
  = help: this function's return type contains a borrowed value, but the signature does not say whether it is borrowed from `x` or `y`
```

Rust can't tell if the reference being returned in `x` or `y` and we don't know
either!

We know that the we want the lifetime of the return value to be either the
lifetime `x` or `y`, but we won't know which one until the function is called
at runtime.

Also, the borrow checker does not know the relationship between the return
values either. Is the return always the lifetime of `x`, or maybe `y`, or maybe
it depends?

In this case, we need to manually define the relationship between the
references for the borrow checker.
