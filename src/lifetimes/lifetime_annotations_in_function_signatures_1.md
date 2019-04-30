# Lifetime Annotations in Function Signatures

Now, let's fix our `longest` function:

```rust
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

Like generic type parameters, we place our generic lifetime parameter `'a`
inside the angle brackets after the function name.

By attaching `'a` to the two function parameters, we're telling Rust that both
string slices must live _at least as long_ as `'a`.

By attaching `'a` to the function return, we're telling Rust that the string
slice returned will live _at least as long_ as `'a`.

These are the constraints we want to enforce. We have communicated to the
borrow checker that it __must__ be enforced.

Lifetime annotations go in the function signature instead of the function body
since it very difficult for Rust to determine the lifetimes of the parameters
or return value on its own.

We must annotate the lifetimes manually.
