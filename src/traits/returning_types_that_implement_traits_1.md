# Returning Types that Implement Traits

We can use the `impl Trait` syntax in the return position as well:

```rust,ignore
fn returns_summarizable() -> impl Summary {
    Tweet {
        username: String::from("horse_ebooks"),
        content: String::from("of course, as you probably already know, people"),
        reply: false,
        retweet: false,
    }
}
```

`returns_summarizable` returns a type that implements `Summary`, but does not
specify the concrete type.

This syntax is especially useful in the context of iterators an closures since
the `impl Trait` return syntax lets us specify functions that return a type
that implements the `Iterator` trait without needing to write out a long type.
