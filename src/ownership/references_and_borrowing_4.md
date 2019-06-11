# References and Borrowing

What is actually happening when we call `calculate_length`?

```rust,ignore
// `s` is a reference to a string
fn calculate_length(s: &String) -> usize {
  s.len()
} // When `s` goes out of scope, nothing happens because
  // because a reference does not have ownership of
  // values
```

Having references as function parameters is called _borrowing_.
