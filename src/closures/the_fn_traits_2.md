# The `Fn` Traits

When a closure is created, Rust infers which trait to use based on how the
closure uses the values from the environment.

- All closures implement `FnOnce`.
- Closures that don't move the captured variables also implement `FnMut`.
- Closures that don't need mutable access to the captured variables also
  implement `Fn`.

In our example, the `equal_to_x` closure only borrows `x` immutably from the
environment and therefore has the `Fn` trait.

```rust
fn main() {
    let x = 4;

    let equal_to_x = |z| z == x;

    let y = 4;

    assert!(equal_to_x(y));
}
```
