# Answer 4

Let's enumerate all the concrete types created:

```rust,editable
struct Bar_Foo;
struct Bar_i32;
struct Bar_str;

impl Bar_Foo {
    fn name_foo(&self) {
        println!("Bar<Foo>");
    }
}

impl Bar_i32 {
    fn name_t(&self) {
        println!("Bar<T>");
    }
}

impl Bar_str {
    fn name_t(&self) {
        println!("Bar<T>");
    }
}

fn main() {
    let x = Bar_Foo;
    let y = Bar_i32;
    let z = Bar_str;

    x.name_foo();
    y.name_t();
    z.name_t();
}
```

Do you notice anything here? Specifically, are there any tradeoffs associated
with _monomorphization_?
