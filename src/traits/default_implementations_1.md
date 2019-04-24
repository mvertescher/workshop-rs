# Default Implementations

It's useful for reuse to provide default behaviors for some methods of a trait
instead of forcing types to reimplement them.

We can always keep or override each method's default behavior.

Let's give the `summarize` method a default implementation:

```rust
pub trait Summary {
    fn summarize(&self) -> String {
        String::from("(Read more...)")
    }
}

pub struct NewsArticle {
    pub headline: String,
    pub location: String,
    pub author: String,
    pub content: String,
}

impl Summary for NewsArticle {};

let article = NewsArticle {
    headline: String::from("Bruins win the Stanley Cup Championship!"),
    location: String::from("Boston, MA, USA"),
    author: String::from("GFY"),
    content: String::from("The Boston Bruins once again are the best
    hockey team in the NHL."),
};

println!("New article available! {}", article.summarize())
```

We can omit an implementation for `summary` in `impl Summary for NewsArticle
{};` and are still able to call the default `summary` function.
