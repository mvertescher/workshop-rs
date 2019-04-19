# Variable Shadowing

We can shadow existing variables in a scope:

```rust
fn main() {
    let x = 7;
    let x = x * x;
    println!("The value of x is: {}", x);
}
```

```plaintext
$ cargo run
 Compiling test-rs v0.1.0 (/home/mv/dev/test-rs)
  Finished dev [unoptimized + debuginfo] target(s) in 0.20s
   Running `target/debug/test-rs`
The value of x is: 49
```

We're effectively creating a new variable with the same name.
