# Return Values and Scope

Consider this:

```rust
fn main() {
  let s = gives_ownership();
  let s = takes_then_gives_ownership(s);
  takes_ownership(s);
}

fn gives_ownership() -> String {
  String::from("hello")
}

fn takes_then_gives_ownership(s: String) -> String {
  s
}

fn takes_ownership(s: String) {
  println!("{}", s);
} // String `s` is `drop`ed here
```

This prints `hello`! However, this is kinda tedious carrying around ownership
all the time!
