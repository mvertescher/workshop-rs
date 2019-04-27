# Lifetime Elision

We don't need to annotate lifetime parameters in some situations:

```rust,editable
// fn first_word<'a>(s: &'a str) -> &'a str {
fn first_word(s: &str) -> &str {
    let bytes = s.as_bytes();

    for (i, &item) in bytes.iter().enumerate() {
        if item == b' ' {
            return &s[0..i];
        }
    }

    &s[..]
}
```

In the process of using the language, the Rust team found that programmers were
entering the same lifetime annotations over and over again in particular
situations.

The borrow checker _can infer_ lifetimes in some situations.
