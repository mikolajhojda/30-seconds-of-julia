---
title: harmonic_mean
tags: math,intermediate
---

The snippet calculates the harmonic mean of two or more numbers.

Use `inv.()` to get the inverse of each argument, add them using `sum()`, then divide the sum by the number of arguments passed, calculated using `length()`.
Finally use `inv()` to invert the result again and get the harmonic mean.

```jl
function harmonic_mean(args...)
  return inv(sum(inv.(args))/length(args))
end
```

```jl
harmonic_mean(0.5, 2) # 0.8
```
