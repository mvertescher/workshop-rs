# Variables

In Rust, we have to explicitly add the `mut` keyword to make a variable
mutable.

```rust
fn main() {
  let mut x = 7;
  x = 8;
}
```

In this particular example, we some warnings:

```plaintext
$ cargo run
   Compiling test-rs v0.1.0 (/home/mv/dev/test-rs)
warning: variable `x` is assigned to, but never used
 --> src/main.rs:2:13
  |
2 |     let mut x = 7;
  |             ^
  |
  = note: #[warn(unused_variables)] on by default
  = note: consider using `_x` instead

warning: value assigned to `x` is never read
 --> src/main.rs:3:5
  |
3 |     x = 8;
  |     ^
  |
  = note: #[warn(unused_assignments)] on by default
```
