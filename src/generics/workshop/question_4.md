# Question 4

How is the code _monomorphized_ at compile time?

```rust
struct Foo;
struct Bar<T>(T);

impl Bar<Foo> {
    fn name_foo(&self) {
        println!("Bar<Foo>");
    }
}

impl<T> Bar<T> {
    fn name_t(&self) {
        println!("Bar<T>");
    }
}

fn main() {
    let x = Bar(Foo);
    let y = Bar(10);
    let z = Bar("foo");

    x.name_foo();
    y.name_t();
    z.name_t();
}
```
