# Ways Variable and Data Interact: Move

Back to our example, what happens when we assign `s1` to `s2`..

```rust,ignore
let s1 = String::from("hello");
let s2 = s1;
```

![String assignment](https://doc.rust-lang.org/book/img/trpl04-02.svg)

When we assign `s1` to `s2`, we only copy the data on the stack. We do not copy
the heap data.
