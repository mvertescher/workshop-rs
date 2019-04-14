# Removing Duplication

We can further reduce duplication by creating a _generic type parameter_ for
the type of the array.

The type parameter `T` must be declared before use: `fn largest<T>`.

Now we can define a single `largest` function:

```rust,ignore
fn largest<T>(list: &[T]) -> T {
    let mut largest = list[0];

    for &item in list.iter() {
        if item > largest {
            largest = item;
        }
    }

    largest
}

fn main() {
    let number_list = vec![34, 50, 25, 100, 65];

    let result = largest(&number_list);
    println!("The largest number is {}", result);

    let char_list = vec!['y', 'm', 'a', 'q'];

    let result = largest(&char_list);
    println!("The largest char is {}", result);
}
```

Unfortunately, this does not compile...

```plaintext
error[E0369]: binary operation `>` cannot be applied to type `T`
 --> src/main.rs:5:12
  |
5 |         if item > largest {
  |            ^^^^^^^^^^^^^^
  |
  = note: `T` might need a bound for `std::cmp::PartialOrd`
```

The compiler is telling us that `>` may _not_ work for all types `T`.

We need to introduce _traits_ to solve this problem. Stay tuned!
