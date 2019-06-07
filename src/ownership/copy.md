# Stack-Only Data: Copy

For simple data, we say the type is `copy` instead of `clone`.

```rust
let x = 5;
let y = x;

println!("x = {}, y = {}", x, y);
```
