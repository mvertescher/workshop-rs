# Where Clauses

When we have many trait bounds and many types, things can become unwieldy:

```rust,ignore
fn some_function<T: Display + Clone, U: Clone + Debug>(t: T, u: U) -> i32 {
```

We can use a `where` clause for complex situations:

```rust,ignore
fn some_function<T, U>(t: T, u: U) -> i32
    where T: Display + Clone,
          U: Clone + Debug
{
```

The function signature is _less_ cluttered and more clear!
