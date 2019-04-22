# Recap

_Traits_ define shared behavior between types.

- We can implement a trait on a type as long as the trait or the type or both are
defined in the local crate.
- We can provide default implementations of trait methods.

_Trait bounds_ specify the behavior of generic type parameters.

- _Where clauses_ enable us to express complex trait bounds.
- We can write functions that return types that implement traits using `impl
  Trait` as long as only one concrete type is ever returned.
- We can conditionally implement methods for types that have generic type
  parameters by placing trait bounds on the generic type parameters.

Trait and trait bounds enable us to write code using generics that has specific
behavior.

In a dynamically typed language, we would get errors at compile time if we call
a method on a type that was not implemented.

In Rust, we check at compile time _and_ don't suffer any performance penalties.
