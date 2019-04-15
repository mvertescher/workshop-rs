# Performance

Let's look at an example of two different concrete types:
`Option<i32>` and `Option<f64>`.

```rust
let integer = Some(5);
let float = Some(5.0);
```

The Rust compiler performs _monomorphization_ on the code above to something
like below.

```rust
enum Option_i32 {
    Some(i32),
    None,
}

enum Option_f64 {
    Some(f64),
    None,
}

fn main() {
    let integer = Option_i32::Some(5);
    let float = Option_f64::Some(5.0);
}
```

There is no runtime cost! This code is compiled _exactly_ as if we created two
separate definitions.
