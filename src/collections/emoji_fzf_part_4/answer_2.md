# Answer 2

> Refactor `emoji-fzf` by adding an `args` module that contains a function
> `parse()`.
>
> `parse()` should return a `Command` enum with variants that contain any
> argument data.
>
> `main()` should use the `Command` from `parse()` to call the appropriate
> handler.

```rust,ignore
extern crate clap;

enum Command {
    Get(String),
    Preview,
}

fn main() {
    let command = args::parse();

    match command {
        Command::Get(name) => display_emoji(&name),
        Command::Preview => preview_emojis(),
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

fn preview_emojis() {
    for emoji in emojis::EMOJIS {
        println!("{}", emoji.0);
    }
}

mod args {
    use super::Command;

    use clap::{crate_name, crate_description, crate_version, crate_authors};
    use clap::{App, Arg, SubCommand};

    pub(super) fn parse() -> Command {
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
                Command::Get(m.value_of("name").unwrap().to_string())
            }
            ("preview", _) => {
                Command::Preview
            }
            _ => std::process::exit(0),
        }
    }
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
