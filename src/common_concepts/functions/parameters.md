# Parameters

Functions can take _paramters_:

```rust
fn main() {
  another_function(10);
}

fn another_function(x: u32) {
  println!("Another function: x = {}.", x);
}
```

_Type annotations_ for parameters are required!
