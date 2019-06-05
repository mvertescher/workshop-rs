# Ways Variable and Data Interact: Move

`s1` is invalidated after _move_ to `s2`:

![Move invalidation](https://doc.rust-lang.org/book/img/trpl04-04.svg)

Eventually, when `s2` goes out of scope, it is freed! (not `s1`)
