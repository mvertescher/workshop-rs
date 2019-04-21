# Implementing a Trait

Let's now use the `summary` method from the `Summary` trait:

```rust
pub trait Summary {
    fn summarize(&self) -> String;
}

pub struct Tweet {
    pub username: String,
    pub content: String,
    pub reply: bool,
    pub retweet: bool,
}

impl Summary for Tweet {
    fn summarize(&self) -> String {
        format!("{}: {}", self.username, self.content)
    }
}

fn main() {
    let tweet = Tweet {
        username: String::from("horse_ebooks"),
        content: String::from("of course, as you probably already know, people"),
        reply: false,
        retweet: false,
    };

    println!("1 new tweet: {}", tweet.summarize())
}
```

We've define our trait and type locally here so we don't need to bring anything
into scope.

If we wanted to implement an external trait on our local type, we would need to
bring the trait into scope first.

Alternatively, we could implement a local trait on an external type.

But, we cannot implement external traits on external types.

This restriction is part of a property of programs called _coherence_,
specifically, the _orphan rule_, that ensures you cannot break other peoples
code and vice-versa.

Without this rule, two crates could implement the same trait for the same type,
and Rust would not know which implementation to use.
