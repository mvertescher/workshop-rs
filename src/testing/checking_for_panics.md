# Checking for Panics

Occasionally, we want to ensure that a function will panic in a test when given
certain inputs.

We can use the `#[should_panic]` attribute for these situations.

We can even add an attribute parameter to `#[should_panic]` called `expected`
where we can ensure that the correct panic string was produced.

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
fn is_prime(n: i64) -> bool {
    if n < 0 {
        panic!("Natural numbers only please!");
    }

#    if n <= 1 {
#        return false;
#    }
#    let n = n as u64;
#    first_factor(n) == n
    // --snip--
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn is_seven_prime() {
        assert!(is_prime(7));
    }

    #[test]
    #[should_panic]
    fn is_negative_ten_prime() {
        assert!(is_prime(-10));
    }

    #[test]
    #[should_panic(expected = "Positive integers only please!")]
    fn is_negative_twenty_prime() {
        assert!(is_prime(-20));
    }
}
```

The panics were captured, but one test failed because a panic string mismatch.

```plaintext
running 3 tests
test tests::is_seven_prime ... ok
test tests::is_negative_ten_prime ... ok
test tests::is_negative_twenty_prime ... FAILED

failures:

---- tests::is_negative_twenty_prime stdout ----
thread 'tests::is_negative_twenty_prime' panicked at 'Natural numbers only please!', src/lib.rs:17:9
note: Panic did not include expected string 'Positive integers only please'
```
