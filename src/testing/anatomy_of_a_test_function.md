# Anatomy of a Test Function

When we create a new library crate with `cargo` an sample test is generated.

```sh
$ cargo new autotest  --lib
    Created library `autotest` package
```

In `src/lib.rs`, we find a test called `it_works`.

```rust
#[cfg(test)]
mod tests {
    #[test]
    fn it_works() {
        assert_eq!(2 + 2, 4);
    }
}
```

Above, we need to specify which functions are tests using the `#[test]`
attribute for the functions since there could be private functions in the
`tests` module.

If we run `cargo test` on our crate, we get:

```plaintext
running 1 test
test tests::it_works ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out

   Doc-tests autotest

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out
```

Although we only have a single test here, we can have multiple test functions
in the `tests` module.
