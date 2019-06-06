# Ways Variable and Interact: Clone

Sometimes, we may want to make a 'deep' copy.

```rust
let s1 = String::from("hello");
let s2 = s1.clone();
println!("s1 = {}, s2 = {}", s1, s2);
```

There are now two `String`s on the heap!
