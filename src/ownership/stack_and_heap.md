# Stack and Heap

To refresh, we have the following in C:

```c
int main() {
  // Allocate an integer on the heap
  // `ptr` is stack local
  int *ptr = (int *) malloc(sizeof(int));
  // Do some stuff with `ptr`
  free(ptr);
}
```

Like C, Rust allocate everything on the stack by default.

With the Rust standard library, we can allocate data on the heap.
