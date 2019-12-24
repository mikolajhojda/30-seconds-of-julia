---
title: intersection_by
tags: array,intermediate
---

Finds the intersection of two arrays `a` and `b` after applying a function `func` to every element in the two arrays.

Use `func.()` on both arrays to get the function-processed array, and run `intersect()` on the returned function-processed arrays.

```jl
function intersection_by(a, b, func)
  return intersect(func.(a), func.(b))
end
```

```jl
intersection_by([1, 2, 3, 4, 5], [0, 1, 2, 3], x -> x + 1) # [2, 3, 4]
```
