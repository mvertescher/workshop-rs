# Question 3

Does this compile? If so, what is printed?

```rust,ignore
struct Foo;
struct Bar<T>(T);

impl Bar<Foo> {
    fn name(&self) {
        println!("Bar<Foo>");
    }
}

impl<T> Bar<T> {
    fn name(&self) {
        println!("Bar<T>");
    }
}

fn main() {
    let x = Bar(Foo);
    let y = Bar(10);
    let z = Bar("foo");

    x.name();
    y.name();
    z.name();
}
```
