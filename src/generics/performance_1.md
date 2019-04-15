# Performance

In Rust, the implementation of generics is optimised for performance.

There is no dynamic runtime cost. Code using generics is no slower that it
would be using concrete types.

Rust accomplishes this by performing _monomorphization_ of code that is using
generics at compile time.

> _Monomorphization_ is the process of turning generic code into specific code
> by filling in the concrete that are used when compiled.

In other words,

> _Monomorphization_ is the conversion from polymorphic to monomorphic code.

This process is similar to the way C++ templates compile.
