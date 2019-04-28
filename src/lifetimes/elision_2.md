# Lifetime Elision

The patterns programmed into Rust's analysis of references are called the
_lifetime elision rules_.

There are three rules:

1. Each parameter that is a reference gets its own lifetime parameter
    - One lifetime parameter: `fn foo<'a>(x: &'a i32)`
    - Two lifetime parameters: `fn foo<'a, 'b>(x: &'a i32, y: &'b i32)`

2. If there is exactly one input lifetime parameter, that lifetime is assigned
   to all output lifetime parameters.
    - For example: `fn foo<'a>(x: &'a i32) -> &'a i32`

3. If there are multiple input lifetime parameters and one of them is `&self`
   or `&mut self`, the lifetime of `self` is assigned to all output lifetime
   parameters.
