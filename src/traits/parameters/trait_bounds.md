# Trait Bounds Syntax

If we need to impose multiple trait bounds on a type we use the `+` operator:

```rust
use std::fmt;

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

impl fmt::Display for Text {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "{}", self.content)
    }
}

pub fn notify<T: Summary + fmt::Display>(item: T) {
    println!("Breaking news! {} {}", item, item.summarize());
}

let text = Text { content: String::from("This is a text...") };
notify(text);
```
