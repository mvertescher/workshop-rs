# Answer 2

Let's annotate the lifetime parameters:

```rust,editable
#[derive(Debug)]
struct Message<'a, 'b> {
    name: &'a str,
    data: &'b [u32],
}

impl<'a, 'b> Message<'a, 'b> {
    // Set the new name and return the old one
    fn update_name(&mut self, name: &'a str) -> &str {
        let old = self.name;
        self.name = name;
        old
    }

    // Deconstruct the message
    fn decompose(self) -> (&'a str, &'b [u32]) {
        (self.name, self.data)
    }
}

fn main() {
    let name = "numbers";
    let data = [3, 5, 1, 6, 2];

    let mut message = Message {
        name: &name,
        data: &data,
    };

    println!("original message: {:?}", message);
    println!("old name: {:?}", message.update_name("yolo"));
    println!("updated message: {:?}", message);
    println!("decomposed: {:?}", message.decompose());
}
```
