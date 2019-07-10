# Answer 1

The last code block is a tricky. Here's the original code:

```rust,compile_fail
fn main() {
    let hello = String::from("hello");
    let mutate = |s| s.truncate(4);
    mutate(hello);
    println!("{}", hello);
}
```

We need to add a type annotations to the closure since the type is unclear:

```rust,compile_fail
fn main() {
    let hello = String::from("hello");
    let mutate = |s: String| s.truncate(4);
    mutate(hello);
    println!("{}", hello);
}
```

Finally, we need to make `hello` and the closure parameter mutable:

```rust
fn main() {
    let mut hello = String::from("hello");
    let mutate = |s: &mut String| s.truncate(4);
    mutate(&mut hello);
    println!("{}", hello);
}
```
