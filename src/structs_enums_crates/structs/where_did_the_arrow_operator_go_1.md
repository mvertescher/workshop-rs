# Where did `->` go?

In C/C++ we must keep track of pointers:

```c
context.something();
// Or if context is a pointer...
context->something()
// That desugars to...
(*context).something()
```
