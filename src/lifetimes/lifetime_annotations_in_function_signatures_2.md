# Lifetime Annotations in Function Signatures

Let's inspect the lifetime constraints we have placed on the `longest`
function:

```rust
# fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
#     if x.len() > y.len() {
#         x
#     } else {
#         y
#     }
# }
fn main() {
    let string1 = String::from("long string is long");

    {
        let string2 = String::from("xyz");
        let result = longest(string1.as_str(), string2.as_str());
        println!("The longest string is {}", result);
    }
}
```

The borrow checker approves of this since the lifetime of `string2` is at least
as long as the lifetime of `result`.

What happens if we try to print out `result` in the outer scope?

```rust,ignore
# fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
#     if x.len() > y.len() {
#         x
#     } else {
#         y
#     }
# }
fn main() {
    let string1 = String::from("long string is long");
    let result;
    {
        let string2 = String::from("xyz");
        result = longest(string1.as_str(), string2.as_str());
    }
    println!("The longest string is {}", result);
}
```

The borrow checker catches this!

```plaintext
error[E0597]: `string2` does not live long enough
  --> src/main.rs:13:44
   |
13 |         result = longest(string1.as_str(), string2.as_str());
   |                                            ^^^^^^^ borrowed value does not live long enough
14 |     }
   |     - `string2` dropped here while still borrowed
15 |     println!("The longest string is {}", result);
16 | }
   | - borrowed value needs to live until here
```

The borrow checker tells us exactly where the lifetime of `string2` ends and
how the lifetime of `result` outlives it.

`result` is not valid in the outer scope since `string2` is not!
