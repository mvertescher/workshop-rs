# Today

Let's review the original alias for `emoji-fzf`:

```bash
alias emoj="emoji-fzf preview | \
    fzf --preview 'emoji-fzf get --name {1}' | \
    cut -d \" \" -f 1 | \
    emoji-fzf get"
```

The `name` subcommand is done!

We still need to implement the `preview` subcommand that is piped into `fzf`!
