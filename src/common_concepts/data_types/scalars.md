# Scalars

There are several primitive scalar types in Rust:

| Length  | Rust Signed  | Rust Unsigned | C Signed  | C Unsigned |
|---------|--------------|---------------|-----------|------------|
| 8-Bit   | `i8`         | `u8`          | `int8_t`  | `uint8_t`  |
| 16-Bit  | `i16`        | `u16`         | `int16_t` | `uint16_t` |
| 32-Bit  | `i32`        | `u32`         | `int32_t` | `uint32_t` |
| 64-Bit  | `i64`        | `u64`         | `int64_t` | `uint64_t` |
| 128-Bit | `i128`       | `u128`        | None      | None       |
| arch    | `isize`      | `usize`       | `ssize_t`[^1] | `size_t`[^1] |

[^1]: Sort of...
