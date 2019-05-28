# Strings

We can create a new `String` type by using `::` to call a namespaced function.

```rust
let mut s = String::from("hello");
```

We can mutate `String`s by calling a function on the type.

```rust
let mut s = String::from("hello");
// push_str() appends a literal to a String
s.push_str(", world!");
println!("{}", s); // This will print `hello, world!`
```

We _cannot_ mutate `&str` types. Weird.
