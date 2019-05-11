# Abstracting Behavior

We can refactor the `generate_workout` function to only call
`simulated_expensive_calculation` once.

```rust
# use std::thread;
# use std::time::Duration;
#
# fn simulated_expensive_calculation(num: u32) -> u32 {
#    println!("calculating slowly...");
#    thread::sleep(Duration::from_secs(2));
#    num
# }
#
fn generate_workout(intensity: u32, random_number: u32) {
    let expensive_result =
        simulated_expensive_calculation(intensity);

    if intensity < 25 {
        println!(
            "Today, do {} pushups!",
            expensive_result
        );
        println!(
            "Next, do {} situps!",
            expensive_result
        );
    } else {
        if random_number == 3 {
            println!("Take a break today! Remember to stay hydrated!");
        } else {
            println!(
                "Today, run for {} minutes!",
                expensive_result
            );
        }
    }
}
```

Now however, we always call the `simulated_expensive_calculation` function
regardless of whether we use the result.
