# Returning Types that Implement Traits

There's a catch! We can only use `impl Trait` if we're returning a single type.

```rust,ignore
# pub trait Summary {
#     fn summarize(&self) -> String;
# }
#
# pub struct NewsArticle {
#     pub headline: String,
#     pub location: String,
#     pub author: String,
#     pub content: String,
# }
#
# impl Summary for NewsArticle {
#     fn summarize(&self) -> String {
#         format!("{}, by {} ({})", self.headline, self.author, self.location)
#     }
# }
#
# pub struct Tweet {
#     pub username: String,
#     pub content: String,
#     pub reply: bool,
#     pub retweet: bool,
# }
#
# impl Summary for Tweet {
#     fn summarize(&self) -> String {
#         format!("{}: {}", self.username, self.content)
#     }
# }
fn returns_summarizable(switch: bool) -> impl Summary {
    if switch {
        NewsArticle {
            headline: String::from("Penguins win the Stanley Cup Championship!"),
            location: String::from("Pittsburgh, PA, USA"),
            author: String::from("Iceburgh"),
            content: String::from("The Pittsburgh Penguins once again are the best
            hockey team in the NHL."),
        }
    } else {
        Tweet {
            username: String::from("horse_ebooks"),
            content: String::from("of course, as you probably already know, people"),
            reply: false,
            retweet: false,
        }
    }
}
```

```plaintext
error[E0308]: if and else have incompatible types
  --> src/main.rs:43:9
   |
34 |   /     if switch {
35 |   |         NewsArticle {
   |  _|_________-
36 | | |             headline: String::from("Penguins win the Stanley Cup Championship!"),
37 | | |             location: String::from("Pittsburgh, PA, USA"),
38 | | |             author: String::from("Iceburgh"),
39 | | |             content: String::from("The Pittsburgh Penguins once again are the best
40 | | |             hockey team in the NHL."),
41 | | |         }
   | |_|_________- expected because of this
42 |   |     } else {
43 | / |         Tweet {
44 | | |             username: String::from("horse_ebooks"),
45 | | |             content: String::from("of course, as you probably already know, people"),
46 | | |             reply: false,
47 | | |             retweet: false,
48 | | |         }
   | |_|_________^ expected struct `main::NewsArticle`, found struct `main::Tweet`
49 |   |     }
   |   |_____- if and else have incompatible types
   |
   = note: expected type `main::NewsArticle`
              found type `main::Tweet`
```

This is a restriction on the way `impl Trait` is implemented.

We need to discuss Trait Objects to write a function in this way.
