# Mapping Emojis.json

If you recall, [the original emoji file][emoji.json] we used looked something like this:

[emoji.json]: https://github.com/muan/emojilib/blob/master/emojis.json

```json
{
  "grinning": {
    "keywords": ["face", "smile", "happy", "joy", ":D", "grin"],
    "char": "😀",
    "fitzpatrick_scale": false,
    "category": "people"
  },
  "grimacing": {
    "keywords": ["face", "grimace", "teeth"],
    "char": "😬",
    "fitzpatrick_scale": false,
    "category": "people"
  },

  ...
}
```

We had to use `jq` and `sed` to extract a Rust data structure from the format...
