# Iterating over Values

To iterate over immutable references:

```rust,editable
fn main() {
    let v: Vec<u32> = vec![100, 32, 57];
    for i in &v {
        println!("{}", i);
        // Uncomment below to see the type of `i`!
        // assert_eq!((), i);
    }
}
```

To iterate over mutable references:


```rust
let mut v = vec![100, 32, 57];
for i in &mut v {
    *i += 50;
}

println!("{:?}", v);
```

Note: we need to _dereference_ `i` using `*` before modifying.
