# Dangling Pointers

In C, it is possible for us to write:

```c
int main() {
  int *p = (int *) malloc(sizeof(int));
  free(p);
  printf("%d", *p);  // Uh oh!
}
```

How does Rust handle this case?
