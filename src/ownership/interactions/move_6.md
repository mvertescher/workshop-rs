# Ways Variable and Data Interact: Move

Back to our example, what happens if we try to use `s1` after moving?

```rust,compile_fail
let s1 = String::from("hello");
let s2 = s1;
println!("{} world!", s1);
```
