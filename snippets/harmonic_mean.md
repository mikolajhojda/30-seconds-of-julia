---
title: harmonic_mean
tags: math,statistics,intermediate
---

The snippet calculates the harmonic mean of two or more numbers.

Use `inv.()` to get the inverse of each argument, then add them using `sum()`, then divide the sum by the number of arguments passed (using `length()`) and finally invert the result again to get the harmonic mean.

```jl
function harmonic_mean(args...)
  return inv(sum(inv.(args))/length(args))
end
```

```jl
harmonic_mean(0.5, 2) # 0.8
```