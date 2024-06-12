---
title: "Making OpenAI Triton easier 🔱 😊"
---

I find writing [triton kernels](triton-lang.org) involves many repetitive tasks, that can be cleanly abstracted away. This allows to write triton code much more in line with how I actually think. It's way more fun, and less mentally draining.

So I made [triton_util](https://github.com/UmerHA/triton_util/), which aims to be a [fastcore](https://fastcore.fast.ai/)-like plug & play addon to OpenAI triton.

With triton util you can e.g. write

```py
tu.load_2d(ptr, sz0, sz1, n0, n1, max0, max1, stride0)
```

instead of
```py
offs0 = n0 * sz0 + tl.arange(0, sz0)
offs1 = n1 * sz1 + tl.arange(0, sz1)
offs = offs0[:,None] * stride0 + offs1[None,:] * stride1
mask = (offs0[:,None] < max0) & (offs1[None,:] < max1)
tl.load(ptr + offs, mask) 
```


Also, I find the `breakpoint_once()` and `print_once()` functions incredibly handy when debugging triton kernels. They breakpoint / print only in one kernel (i.e., `pid=(0,0,0)`)

You can install it via `pip install triton-util`. I suggest importing it like `import triton_util as tu`.

I like to also abbreviations the debugging functions like so: `breakpoint_once, print_once, breakpoint_if, breakpoint_if = tu.breakpoint_once, tu.print_once, tu.breakpoint_if, tu.breakpoint_if`.

Check [triton_util](https://github.com/UmerHA/triton_util/) out!

And let me know what think via [Twitter](https://x.com/UmerHAdil) or umer.hayat.adil@gmail.com.

\- Umer