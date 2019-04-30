# Generic Lifetimes in Functions

Let's consider the case where want to write a function that takes two string
slices and returns the longer slice.

We might use the `longest` function like this:

```rust,ignore
fn main() {
    let string1 = String::from("abcd");
    let string2 = "xyz";

    let result = longest(string1.as_str(), string2);
    println!("The longest string is {}", result);
}
```

We want use slices, which are references, so the `longest` function does not
take ownership of the strings we wish to compare.
