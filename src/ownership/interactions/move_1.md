# Ways Variable and Data Interact: Move

When we assign integers, data is copied on the stack:

```rust,ignore
let x = 5;
let y = x;  // Copy the value of x to y
// There now two `5`s on the stack
```

This is different than `String`s. For example:

```rust,ignore
let s1 = String::from("hello");
let s2 = s1;
```

Are there _two_ strings now?
