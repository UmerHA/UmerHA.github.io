---
title: "Getting ptx from Triton"
collection: smarties
---

You can get the ptx of a triton kernel like so:  `my_kernel.cache[DEVICE_KEY][INPUTS_KEY].asm['ptx']`, where `DEVICE_KEY` and `INPUTS_KEY` are determined like below.

**Case 1 (most likely):** If you've compiled the kernel only for a single device and a single set of inputs, `cache` only has a single key-value mapping, which itself only as a single key-value mapping. So this works:

```py
def value(dict_):
    assert len(dict_)==1, 'dict has more than one value' # we're assuming a single env & a single input set
    return list(dict_.values())[0] # return that single value

value(value(my_kernel.cache)).asm['ptx']
```

**Case 2:** If you've compiled for multiple devices or input sets, you need to find `DEVICE_KEY` and `INPUTS_KEY`. Print `my_kernel.cache.keys()` and select the device key you need, the print the `keys()` for that again to get the inputs key you want.

That's it!

\- Umer
