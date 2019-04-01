# Introducing `Serde` [![Latest Version]][crates.io]

[Latest Version]: https://img.shields.io/crates/v/serde.svg
[crates.io]: https://crates.io/crates/serde

[`Serde`](https://serde.rs/) is a framework for <strong>ser</strong>ializing
and <strong>de</strong>serializing Rust data structures efficiently and
generically.

`serde` supports a handful data formats out of the box including [JSON][json],
[CBOR][cbor], [YAML][yaml], [TOML][toml], [x-www-form-urlencoded][url] and many
more!

[json]: https://github.com/serde-rs/json
[cbor]: https://github.com/pyfisch/cbor
[yaml]: https://github.com/dtolnay/serde-yaml
[toml]: https://github.com/alexcrichton/toml-rs
[url]: https://github.com/nox/serde_urlencoded

Out of the box, `serde` can deserialize many common Rust data structures and
primitive types like `String`, `{integer}`, `Vec<T>` and `HashMap<K,V>`.

A derive attribute is provided to generate implementations for simple data
structures.
