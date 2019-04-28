# Lifetime Annotations in Method Definitions

When we implement methods on a struct with lifetimes, the lifetimes could be
related to the struct fields or the method parameters and return values.

Lifetime names for struct fields always need to be declared after the `impl`
keyword and then used after the struct name.

```rust,ignore
impl<'a> ImportantExcerpt<'a> {
```

For method signatures inside the `impl` block, references might be tied to the
lifetime of references in the struct's fields, or they might be independent.

```rust,ignore
impl<'a> ImportantExcerpt<'a> {
    fn level(&self) -> i32 {
        3
    }
}
```

In the example above, we don't need to annotate the lifetimes because of the
first rule.

```rust,ignore
impl<'a> ImportantExcerpt<'a> {
    fn announce_and_return_part(&self, announcement: &str) -> &str {
        println!("Attention please: {}", announcement);
        self.part
    }
}
```

The first elision rule gives `&self` and `&str` separate lifetimes and the
third elision rule ties the lifetime of `&self` to the return type lifetime.

```rust,ignore
    fn announce_and_return_part(&'a self, announcement: &str) -> &'a str {
```
