# Ownership and Structs

Uh oh!

```plaintext
$ cargo build
   Compiling test-rs v0.1.0 (/home/mv/dev/test-rs)
error[E0106]: missing lifetime specifier
 --> src/main.rs:3:11
  |
3 |     name: &str,
  |           ^ expected lifetime parameter

error[E0106]: missing lifetime specifier
 --> src/main.rs:4:11
  |
4 |     path: &str,
  |           ^ expected lifetime parameter

error: aborting due to 2 previous errors
```

They can! We'll come back to this later!
