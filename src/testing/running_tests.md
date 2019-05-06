# Running Tests

We can send options to `cargo test` by specifying flags before the `--`. Flags
after `--` are sent to the test binary directly.

By default, tests are run in parallel, we can disable this like so:

```sh
$ cargo test -- --test-threads=1
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
