# Mapping Emojis.json

With `serde`, we can map each JSON object to a Rust structure:

```json
{
  "grinning": {
    "keywords": ["face", "smile", "happy", "joy", ":D", "grin"],
    "char": "😀",
    "fitzpatrick_scale": false,
    "category": "people"
  }
}
```

Becomes...

```rust,ignore
#[derive(Deserialize, Debug)]
struct Emoji {
    keywords: Vec<String>,
    #[serde(rename = "char")]
    ch: String,
    fitzpatrick_scale: bool,
    category: String,
}
```
