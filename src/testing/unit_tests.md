# Unit Tests

All tests we have seen so far are considered unit tests in the Rust ecosystem.

> Unit tests in Rust live in the __same file__ as the code they test.

The `#[cfg(test)]` configuration attribute ensures that test code is only
compiled when `cargo test` is called _not_ `cargo build` or `cargo run`.

Unit tests in Rust give us the ability to test internal function that are
not exposed in a public crate API:

```rust
pub fn add_two(a: i32) -> i32 {
    internal_adder(a, 2)
}

fn internal_adder(a: i32, b: i32) -> i32 {
    a + b
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn internal() {
        assert_eq!(4, internal_adder(2, 2));
    }
}
```
