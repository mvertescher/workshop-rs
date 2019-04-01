# Hashing Functions

By default, `HashMap` uses a “cryptographically strong”[^siphash] hashing
function that can provide resistance to Denial of Service (DoS) attacks.

In the interest of performance, an alternative _hasher_ type can be created.

Alternatively, a drop-in replacement can be used like
[https://github.com/Amanieu/hashbrown](https://github.com/Amanieu/hashbrown)
for instance.

[^siphash]: [https://www.131002.net/siphash/siphash.pdf](https://www.131002.net/siphash/siphash.pdf)
