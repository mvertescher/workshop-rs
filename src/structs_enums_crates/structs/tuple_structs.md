# Tuple Structs

Tuple structs in Rust are structures composed with unnamed fields:

```rust
struct Rbg(i32, i32, i32);

let black = Rbg(0, 0, 0);
assert_eq!(0, black.0);
```

This type of structure helps to decrease verbosity in some situations.
