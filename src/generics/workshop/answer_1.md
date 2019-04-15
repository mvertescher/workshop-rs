# Answer 1

No! We missed the type parameter declaration `<T>` after `impl` when declaring
the `impl` block for `Bar<T>`.

```rust,editable
struct Foo;
struct Bar<T>(T);

impl Bar<Foo> {
    fn name_foo(&self) {
        println!("Bar<Foo>");
    }
}

// BAD: impl Bar<T> {
impl<T> Bar<T> {
    fn name_t(&self) {
        println!("Bar<T>");
    }
}

fn main() {}
```

The complier expected `T` to be a concrete type instead of a generic type
parameter!
