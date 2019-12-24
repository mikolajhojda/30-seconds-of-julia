---
title: root_mean_square
tags: array,statistics,intermediate
---

Calculates the root mean square of arguments.

Get the mean of the square of the arguments using `abs2.()` and `length()`. Then, return the square root of this value.

```jl
function root_mean_square(args...)
  return sqrt(sum(abs2.(args))/length(args))
end
```

```jl
root_mean_square(1, 3, 5) # approximately 3.42
```