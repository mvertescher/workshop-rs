# Variables

Variables in Rust are __immutable__ by default.

_All_ variables have a type known at compile time.

Rust has _Type Inference_. This enables us to omit type annotations.

```rust,ignore
fn main() {
    let x = 7;
    x = 8;
}
```

```plaintext
$ cargo run
   Compiling test-rs v0.1.0 (/home/mv/dev/test-rs)
error[E0384]: cannot assign twice to immutable variable `x`
--> src/main.rs:3:5
  |
2 |     let x = 7;
  |         -
  |         |
  |         first assignment to `x`
  |         help: make this binding mutable: `mut x`
3 |     x = 8;
  |     ^^^^^ cannot assign twice to immutable variable

error: aborting due to previous error
```
