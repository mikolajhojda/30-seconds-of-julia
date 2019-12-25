---
title: root_mean_square
tags: math,array,intermediate
---

Calculates the root mean square of the given arguments.

Use `abs2.()` and `length()` to get the mean of the square of `args`. 
Use `sqrt()` to get the square root of this value.

```jl
function root_mean_square(args...)
  return sqrt(sum(abs2.(args))/length(args))
end
```

```jl
root_mean_square(1, 3, 5) # approximately 3.42
```
