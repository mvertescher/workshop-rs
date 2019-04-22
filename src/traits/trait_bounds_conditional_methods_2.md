# Using Trait Bounds to Conditionally Implement Methods

We can also conditionally implement a trait for any type that implements
another trait.

In the standard library, `ToString` is implemented for any type that is
`Display`.

```rust,ignore
impl<T: Display> ToString for T {
    // --snip--
}
```

We can call `to_string` on integers because they implement `Display`:

```rust
let s = 3.to_string();
```
