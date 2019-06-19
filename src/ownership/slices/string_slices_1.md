# String Slices

Here's a quick example:

```rust
let s = String::from("hello world");
let hello = &s[0..5];
let world = &s[6..11];
```

Or alternatively:

```rust
let s = String::from("hello world");
let hello = &s[0..=4];
let world = &s[6..=10];
```

Or even:

```rust
let s = String::from("hello world");
let hello = &s[..=4];
let world = &s[6..];
```

For string slices, we assume ASCII. UTF-8 slices on partial chars will panic.
Slices follow the same borrowing rules as references.
