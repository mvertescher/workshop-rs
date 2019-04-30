# Question 2

Does if this compile? If not, how can we fix this?

```rust,compile_fail,editable
#[derive(Debug)]
struct Message {
    name: &str,
    data: &[u32],
}

impl Message {
    // Set the new name and return the old one
    fn update_name(&mut self, name: &str) -> &str {
        let old = self.name;
        self.name = name;
        old
    }

    // Deconstruct the message
    fn decompose(self) -> (&str, &[u32]) {
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
