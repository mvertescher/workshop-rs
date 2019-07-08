# Move Closures

Closures can be forced to take ownership of their environment by using the
`move` keyword.

```rust,compile_fail
fn main() {
    let x = vec![1, 2, 3];

    let equal_to_x = move |z| z == x;

    println!("can't use x here: {:?}", x);

    let y = vec![1, 2, 3];

    assert!(equal_to_x(y));
}
```

`move` closures are useful when passing a closure to a new thread so data is
owned by the new thread.  We'll revisit `move` when we talk about concurrency.
