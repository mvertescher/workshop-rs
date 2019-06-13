# Multiple Mutable References

You can have multiple mutable references, just not simultaneous ones:

```rust
let mut s = String::from("hello");
{
  let r1 = &mut s;
  println!("{}", r1);
} // r1 goes out of scope here..
  // We can make a new reference with no problems.
let r2 = &mut s;
println!("{}", r2);
```
