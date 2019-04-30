# Question 1

For each example:
- Does this compile?
- Annotate the lifetimes!

```rust,ignore
fn last_word(s: &str) -> &str {
#    let i = s.rfind(" ")
#        .map(|x| x + 1)
#        .unwrap_or(0);
#    &s[i..]
    // -snip-
}
```

```rust,ignore
fn first_occurrence(s: &str, substring: &str) -> &str {
    // -snip-
#   s
}
```

```rust,ignore
fn first_two_occurrences(s: &str, substring: &str) -> (&str, &str) {
    // -snip-
#   s
}
```
