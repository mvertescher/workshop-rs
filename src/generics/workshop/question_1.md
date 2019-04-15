# Question 1

Does this compile?

```rust,ignore
struct Foo;
struct Bar<T>(T);

impl Bar<Foo> {
    fn name_foo(&self) {
        println!("Bar<Foo>");
    }
}

impl Bar<T> {
    fn name_t(&self) {
        println!("Bar<T>");
    }
}
```
