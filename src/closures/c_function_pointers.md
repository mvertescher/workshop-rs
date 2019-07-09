# C Function Pointers

C does not have closures,[^1] but function pointers can provide something similar.

Using function pointers, we can implement closures:

```c
#include <assert.h>
#include <stdio.h>

typedef struct sClosure sClosure;

typedef void* (*tFunction)(void *env, void *args);

struct sClosure {
    tFunction fn;
    void *env;
};

sClosure build_closure(tFunction fn, void *env) {
    sClosure c = {
        .fn = fn,
        .env = env,
    };
    return c;
}

void* call_closure(sClosure *c, void *args) {
    return c->fn(c->env, args);
}

// This function adds two integers together!
void* g(void *env, void *args) {
    return (void *) (*(long *) env) + (*(long *) args);
}

// This function returns a closure
sClosure f(void *env) {
    return build_closure(&g, env);
}

void main() {
    long x = 1;
    sClosure a = f(&x);

    long arg = 5;
    long result = (long) call_closure(&a, &arg);
    assert(6 == result);
}
```

Quite unsafe and verbose!

[^1]: There are C libraries that provide closure like constructs. GNU
[libffcall](libffcall) provides closures with variable arguments as first-class
C functions. Apple also has a non-standard C language extension called
[blocks](blocks) to provide closures.

[blocks]: https://en.wikipedia.org/wiki/Blocks_%28C_language_extension%29
[libffcall]: https://savannah.gnu.org/projects/libffcall/
