# Answer 1

The last code block is a tricky. Here's the original code:

```rust,compile_fail
fn main() {
    let hello = String::from("hello");
    let mutate = |s| s.truncate(4);
    hello.truncate(3);
    mutate(hello);
}
```

We need to add a type annotations to the closure since the type is unclear:

```rust,compile_fail
fn main() {
    let hello = String::from("hello");
    let mutate = |s: String| s.truncate(4);
    hello.truncate(3);
    mutate(hello);
}
```

Finally, we need to make `hello` and the closure parameter mutable:

```rust
fn main() {
    let mut hello = String::from("hello");
    let mutate = |mut s: String| s.truncate(4);
    hello.truncate(3);
    mutate(hello);
}
```
