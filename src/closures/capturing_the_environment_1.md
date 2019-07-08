# Capturing the Environment

So far, we've only used closures as inline anonymous functions.

Unlike functions, closures can also capture their environment and access
variables from the scope in which they are defined.

For example, `x` is captured in the example below:

```rust
fn main() {
    let x = 4;

    let equal_to_x = |z| z == x;

    let y = 4;

    assert!(equal_to_x(y));
}
```

If we try to use a function instead, we run into issues:

```rust,compile_fail
fn main() {
    let x = 4;

    fn equal_to_x(z: i32) -> bool { z == x }

    let y = 4;

    assert!(equal_to_x(y));
}
```
