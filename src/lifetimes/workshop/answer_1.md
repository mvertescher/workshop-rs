# Answer 1

The `last_word` function compiles just fine:

```rust
// fn last_word(s: &'a str) -> &'a str {
fn last_word(s: &str) -> &str {
    // -snip-
#   s
}
```

The original `first_occurrence` function did not compile. We need to add a
lifetime annotation `'a`:

```rust
// fn first_occurrence(s: &str, substring: &str) -> &str {
fn first<'a>(s: &'a str, substring: &str) -> &'a str {
    // -snip-
#   s
}
```

Similarly, the original `first_two_occurrences` function did not compile. We
need to add a lifetime annotation `'a`:

```rust
fn first_two_occurrences<'a>(s: &'a str, substring: &str) -> (&'a str, &'a str) {
    // -snip-
#   (s, s)
}
```

