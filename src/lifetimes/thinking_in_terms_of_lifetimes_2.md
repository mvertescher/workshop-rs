# Thinking in Terms of Lifetimes

When returning a reference from a function, the lifetime parameter of the
return type must match the lifetime of one of the input parameters.

If the lifetime parameter of the return type does not match one of the
lifetimes of the input types, it must refer to a lifetime of a value created
within the function itself. This is dangling reference.

Consider this as an example:

```rust,ignore
fn longest<'a>(x: &str, y: &str) -> &'a str {
    let result = String::from("really long string");
    result.as_str()
}
```

Even though we've given the return type a lifetime parameter, this
implementation fails because the return lifetime is not related to any of the
input parameters.

```plaintext
error[E0597]: `result` does not live long enough
 --> src/main.rs:6:5
  |
6 |     result.as_str()
  |     ^^^^^^ borrowed value does not live long enough
7 | }
  | - borrowed value only lives until here
  |
note: borrowed value must be valid for the lifetime 'a as defined on the function body at 4:12...
 --> src/main.rs:4:12
  |
4 | fn longest<'a>(x: &str, y: &str) -> &'a str {
  |            ^^
```

The lifetime of `result` ends just as we want to return it from the function!
This is a dangling reference!

Ultimately, the lifetime syntax is about associating the lifetimes of the input
parameters to return values from functions. This fills in missing information
for the borrow checker to maintain memory safety.
