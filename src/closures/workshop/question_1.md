# Question 1

Do these compile and why? If not, how can we fix them?

```rust
fn main() {
    let hello = "hello";
    let print = |s| println!("{} {}", hello, s);
    print("world");
    print("ten");
}
```

```rust,compile_fail
fn main() {
    let hello = "hello";
    let print = |s| println!("{} {}", hello, s);
    print("world");
    print(10);
}
```

```rust,compile_fail
fn main() {
    let hello = String::from("hello");
    let mutate = |s| s.truncate(4);
    hello.truncate(3);
    mutate(hello);
}
```
