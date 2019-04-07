# `panic!`

When a `panic!` occurs...
- A failure message will be printed
- The stack is unwound and cleaned up
- The program will quit

When _optimizing for size_, we may just want to _abort_ (end the program
without cleaning up). This feature can be enabled in a `Cargo.toml`:

```toml
[profile.release]
panic = 'abort'
```
A panic reports the file and line number of the `panic!` call:

```rust,should_panic,panics
fn main() {
    panic!("crash and burn");
}
```

A `panic!` can occur in a dependant crate...
