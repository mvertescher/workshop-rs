# The Borrow Checker in Rust 2018

The borrow check now behaves like this:

```rust,ignore
fn main() {
    let mut s = String::from("hello");
    let r1 = &mut s;     // 'lifetime of `r1` --+
    println!("{}", r1);  //                     |
//  ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+

    let r2 = &mut s;     // 'lifetime of `r2` --+
    println!("{}", r2)   //                     |
//  ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~+
}
```

```plaintext
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.01s
     Running `target/debug/test-rs`
hello
hello
```
