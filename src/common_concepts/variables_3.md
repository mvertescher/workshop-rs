# Variables

Let's add `_` to our variable to tell the compiler that it is currently unused.

Using `_` is useful in situations where we _may_ want to act on a value later.
For now, however, it is ignored.

```rust
fn main() {
    let mut _x = 7;
    _x = 8;
}
```

```plaintext
$ cargo run
 Compiling test-rs v0.1.0 (/home/mv/dev/test-rs)
  Finished dev [unoptimized + debuginfo] target(s) in 0.19s
   Running `target/debug/test-rs`
```

Success!
