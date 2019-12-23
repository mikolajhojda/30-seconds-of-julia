---
title: geometric_mean
tags: math,statistics,intermediate
---

The snippet calculates the geometric mean of two or more numbers.

Use `prod()` to get the product of the `args`, then take its n-th root where `n` is the number of arguments passed. The number of arguments passed is calculated using `length()`

```jl
function geometric_mean(args...)
  return prod(args) ^ (1 / length(args))
end
```

```jl
geometric_mean(8, 27, 64) # 24
```