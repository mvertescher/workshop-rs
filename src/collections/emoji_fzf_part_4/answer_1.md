# Answer 1

> Extend `clap::App` to print each emoji name on a new line when the `preview`
> subcommand is called.

```rust,ignore
extern crate clap;

use clap::{crate_name, crate_description, crate_version, crate_authors};
use clap::{App, Arg, SubCommand};

fn main() {
    let matches = App::new(crate_name!())
        .about(crate_description!())
        .version(crate_version!())
        .author(crate_authors!())
        .subcommand(SubCommand::with_name("get")
                    .about("Get unicode emoji given a name")
                    .arg(Arg::with_name("name")
                        .help("Name of the emoji to display")
                        .index(1)
                        .required(true)))
        .subcommand(SubCommand::with_name("preview")
                    .about("Display a list of all available emojis by name"))
        .get_matches();

    match matches.subcommand() {
        ("get", Some(m)) => {
            let name = m.value_of("name").unwrap();
            display_emoji(name);
        }
        ("preview", _) => {
            for emoji in emojis::EMOJIS {
                println!("{}", emoji.0);
            }
        }
        _ => std::process::exit(0),
    }
}

fn display_emoji(name: &str) {
    for emoji in emojis::EMOJIS {
        if name == emoji.0 {
            println!("{}", emoji.1);
            std::process::exit(0);
        }
    }
    std::process::exit(1);
}

mod emojis {
    pub const EMOJIS: &[(&str, &str)] = &[
        ("grinning","😀"),
        ("grimacing","😬"),
        // ...
        ("united_nations","🇺🇳"),
        ("pirate_flag","🏴‍☠️"),
    ];
}
```
