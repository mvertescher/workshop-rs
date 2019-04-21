# Defining a Trait

Trait definitions are a way to group method signatures together to define a set
of behaviors to accomplish some purpose.

Let's define a trait with a single method.

```rust
pub trait Summary {
    fn summarize(&self) -> String;
}
```

We have not defined an implementation for the `summarize` method.

The complier will be responsible for enforcing that types provide an
implementation for `summarize` if the type has the `Summary` trait.

A trait can have multiple methods in its body.
