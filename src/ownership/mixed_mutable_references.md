# Mixed Mutable References

What happens if we mix immutable and mutable references?

```rust,compile_fail
let mut s = String::from("hello");

let r1 = &s; // no problem
let r2 = &s; // no problem
let r3 = &mut s; // BIG PROBLEM

println!("{}, {}, and {}", r1, r2, r3)
```

We _cannot_ have a mutable reference while we have an immutable one!

This could lead to _data races_!
