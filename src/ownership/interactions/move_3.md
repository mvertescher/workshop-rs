# Ways Variable and Data Interact: Move

`String`'s are similar to this in C:

```c
//! A 'safe' String :)
typedef struct {
  void *p;     //! Points at the real data
  size_t len;  //! Current length
  size_t cap;  //! Total capacity
} sString
```

(I may have written this once)
