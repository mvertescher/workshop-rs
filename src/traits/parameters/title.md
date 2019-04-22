# Traits as Parameters

Now that we know how to define traits and implement them on types, we can use
traits as parameters.

Let's look a short example:

```rust
pub trait Summary {
    fn summarize(&self) -> String;
}

pub struct Text {
    pub content: String,
}

impl Summary for Text {
    fn summarize(&self) -> String {
        format!("{}", self.content)
    }
}

pub fn notify(item: impl Summary) {
    println!("Breaking news! {}", item.summarize());
}

let text = Text { content: String::from("This is a text...") };
notify(text);
```

We can call the `notify` function with any type that implements `Summary`.
