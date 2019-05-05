# Testing Equality

We can also use the `assert_eq!` and `assert_nq!` to test equality:

```rust
# fn first_factor(x: u64) -> u64 {
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
# }
#
fn is_prime(n: u64) -> bool {
#    if n <= 1 {
#        return false;
#    }
#    first_factor(n) == n
    // --snip--
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn is_seven_prime() {
        assert_eq!(true, is_prime(7));
    }

    #[test]
    fn is_ten_prime() {
        assert_eq!(true, is_prime(10));
    }
}
```

Let's check out the error message now:

```plaintext
running 2 tests
test tests::is_seven_prime ... ok
test tests::is_ten_prime ... FAILED

failures:

---- tests::is_ten_prime stdout ----
thread 'tests::is_ten_prime' panicked at 'assertion failed: `(left == right)`
    left: `true`,
   right: `false`', src/lib.rs:34:9
   note: Run with `RUST_BACKTRACE=1` environment variable to display a backtrace.
```

Equivalence assertions give us more information than regular `assert`s.
