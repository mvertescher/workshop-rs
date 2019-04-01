# Hashing Functions

By default, `HashMap` uses a “cryptographically strong”[^siphash] hashing
function that can provide resistance to Denial of Service (DoS) attacks.

In the interest of performance, an alternative _hasher_ type can be created.

[^siphash]: [https://www.131002.net/siphash/siphash.pdf](https://www.131002.net/siphash/siphash.pdf)
