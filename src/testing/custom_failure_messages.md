# Custom Failure Messages

Sometimes, we may want to print custom error messages on failures:

```rust
fn first_factor(x: u64) -> u64 {
#     if x % 2 == 0 {
#         return 2;
#     }
#
#     for n in (3..).step_by(2).take_while(|m| m * m <= x) {
#         if x % n == 0 {
#             return n;
#         }
#     }
#
#     return x;
    // --snip--
}
#
# fn is_prime(n: u64) -> bool {
#    if n <= 1 {
#        return false;
#    }
#    first_factor(n) == n
#     // --snip--
# }

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn first_factor_21() {
        let factor = first_factor(21);
        assert!(factor == 7, "The first factor was not 7, but {}", factor);
    }
}
```

We can produce even more informative error messages now.

```plaintext
running 1 test
test tests::first_factor_21 ... FAILED

failures:

---- tests::first_factor_21 stdout ----
thread 'tests::first_factor_21' panicked at 'The first factor was not 7, but 3', src/lib.rs:32:9
note: Run with `RUST_BACKTRACE=1` environment variable to display a backtrace.
```
