# Using Result in Tests

We can also write tests that return a `Result<T, E>`.

Let's modify the `it_works` test slightly:

```rust
#[cfg(test)]
mod tests {
    #[test]
    fn it_works() -> Result<(), String> {
        if 2 + 2 == 4 {
            Ok(())
        } else {
            Err(String::from("two plus two does not equal four"))
        }
    }
}
```

Two things to note:

1. We can't use the `#[should_panic]` annotation on test that return
`Result<T, E>`. We should return and `Err` instead.
2. We can use the `?` operator for convenience.
