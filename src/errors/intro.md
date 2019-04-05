# Introduction

Rust groups errors into two major categories: _recoverable_ and _unrecoverable_.

Sometime operations, like opening a file, can fail at runtime. This is an
example of an error that should be _recoverable_.

Errors that are _unrecoverable_ are the symptom of software bugs.

In Rust:

- _unrecoverable_ errors -> `panic!`
- _recoverable_ errors   -> `Result<T, E>`
