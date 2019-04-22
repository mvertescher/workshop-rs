# Fixing the Largest Function

We can only call the longest function with types that support `Copy` like `i32`
and `char`.

Let's add `Copy` as a trait bound:

```rust,editable
fn largest<T: PartialOrd + Copy>(list: &[T]) -> T {
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


/*
    let string_list = vec![
        String::from("one"),
        String::from("two"),
        String::from("three"),
    ];

    let result = largest(&string_list);
    println!("The largest String is {}", result);
*/
}
```

What happens if our array consists of `String`s?

Can we eliminate our `Copy` trait bound?
