# The Borrow Checker in Rust 2015

In Rust 2015, this example does not compile:

```rust,ignore
fn main() {
    let mut s = String::from("hello");
    let r1 = &mut s;     // 'lifetime of `r1` --+
    println!("{}", r1);  //                     |
                         //                     |
    let r2 = &mut s;     // 'lifetime of `r2` --|-+
    println!("{}", r2)   //                     | |
} // ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+-+
```

```plaintext
error[E0499]: cannot borrow `s` as mutable more than once at a time
 --> src/main.rs:7:19
  |
4 |     let r1 = &mut s;
  |                   - first mutable borrow occurs here
...
7 |     let r2 = &mut s;
  |                   ^ second mutable borrow occurs here
8 |     println!("{}", r2)
9 | }
```

You cannot have two mutable borrows in the same lexical scope.
