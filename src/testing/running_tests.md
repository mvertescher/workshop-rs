# Running Tests

We can send options to `cargo test` by specifying flags before the `--`. Flags
after `--` are sent to the test binary directly.

By default, tests are run in parallel, we can disable this like so:

```sh
$ cargo test -- --test-threads=1
```

Furthermore, `cargo test` captures standard output. Anything we print using
`println!` for example, will not be displayed when running tests.

We can disable standard output capture:

```sh
$ cargo test -- --nocapture
```

`cargo test` will run all tests in our crate by default.

We can test an individual test function by calling the name directly:

```sh
$ cargo test is_seven_prime
```

We can test all functions that start with a particular string. Based on our
previous examples, lets run all tests that start with `is_prime`:

```sh
$ cargo test is_prime
```

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
