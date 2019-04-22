# Trait Bound Syntax

`impl Trait` is syntactic sugar for a longer syntax called a _trait bound_.

```rust,editable
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

fn main() {
    // pub fn notify(item: impl Summary) {
    pub fn notify<T: Summary>(item: T) {
        println!("Breaking news! {}", item.summarize());
    }

    // The following two lines express the same signature
    // pub fn notify_all(item1: impl Summary, item2: impl Summary) {
    pub fn notify_all<T: Summary>(item1: T, item2: T) {
        println!("Breaking news! {} {}", item1.summarize(), item2.summarize());
    }

    let text = Text { content: String::from("This is a text...") };

    notify(text);
    // notify_all(text, text);
}
```

The `<T: Trait>` syntax specifies a trait bound, `Trait`, on `T`.
