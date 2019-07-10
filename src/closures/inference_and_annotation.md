# Type Inference and Annotation

Closures do not require you to annotate the types of the parameters like `fn`
functions.

Let's compare functions to closures:

```rust,ignore
fn  add_one_v1   (x: u32) -> u32 { x + 1 }   // Function
let add_one_v2 = |x: u32| -> u32 { x + 1 };  // Annotated closure
let add_one_v3 = |x|             { x + 1 };  // Closure with braces
let add_one_v4 = |x|               x + 1  ;  // Closure without braces
```

The compiler infers the types of the closure parameters based on the usage:

```rust,compile_fail
let sample_closure = |x| x;

let s = sample_closure(String::from("hello"));
let n = sample_closure(5);
```
