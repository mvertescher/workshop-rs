# Side Note: Clippy Example

Clippy is Rust's auto formatting tool.

```sh
$ cargo clippy
```

In the last example, Clippy can help us catch mis-formatted integers:

```plaintext
    checking test-rs v0.1.0 (/home/mv/dev/test-rs)
warning: long literal lacking separators
 --> src/main.rs:2:18
  |
2 |     let x: u64 = 0x100000002;
  |                  ^^^^^^^^^^^ help: consider: `0x0001_0000_0002`
  |
  = note: #[warn(clippy::unreadable_literal)] on by default
  = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#unreadable_literal
```
