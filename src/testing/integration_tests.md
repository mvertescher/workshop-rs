# Integration Tests

Integration tests in Rust test code just as an external user would.

These tests can only interact with the external API exposed by the library
crate.

Integration tests in Rust live in the `tests` directory (next to `src`):

```rust,ignore
// Bring our crate into scope
use adder;

#[test]
fn it_adds_two() {
    assert_eq!(4, adder::add_two(2));
}
```

We no longer need `#[cfg(test)]`. Instead, Cargo will compile each file in the
`tests` directory as a separate test crate.

There is one exception to this: files in subdirectories of the `tests` directory
do not get compiled as separate crates or have sections in their test output.

For example, `tests/common/mod.rs` will be ignored.
