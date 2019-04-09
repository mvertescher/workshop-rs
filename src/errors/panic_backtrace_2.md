# `panic!` Backtrace

When working with `cargo`, it is common to run a command like below:

```sh
$ RUST_BACKTRACE=1 cargo run
```

Let's print the backtrace:

```rust,should_panic,panics
fn main() {
#     std::env::set_var("RUST_BACKTRACE", "1");
    let v = vec![1, 2, 3];

    v[99];
}
```

The informative output here is provided by debug symbols that are compiled into
binaries by default.
