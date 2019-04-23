# Introduction

_Traits_ define shared behavior.

_Trait bounds_ can be used to specify the behavior of generic type parameter.

> Note: Traits are similar to a feature often called _interfaces_ in other
> languages, although with some differences.

Traits in Rust are most similar _type classes_ in Haskell:

- It is possible to add traits to arbitrary data types, including primitive
  types.
- Traits can define a default implementation for a method.
- A trait can be used for operator overloading. For example, we can 'redefine'
  `==`.
- Each overloadable operator in Rust has a corresponding trait in the standard
  library.

