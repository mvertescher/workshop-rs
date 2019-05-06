# Ignoring Tests

There is another attribute use to ignore expensive or long tests: `#[ignore]`.

```rust,ignore
#[test]
#[ignore]
fn expensive_test() {
    // code that takes an hour to run
}
```

We can run these tests by passing `--ignored`

```sh
$ cargo test -- --ignored
```
