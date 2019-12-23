---
title: bifurcate_by
tags: array,function,intermediate
---

Splits values into two groups according to a function, which specifies which group an element in the input list belongs to. If the function returns `true`, the element belongs to the first group; otherwise, it belongs to the second group.

Use a list comprehension to build both the `true` returning groups and the `false` returning groups.

```jl
function bifurcate_by(array, func)
  return [[x for x in array if func(x)], [x for x in array if !func(x)]]
end
```

```jl
bifurcate_by(["foo", "blob", "bar", "thing", "abcd"], x -> length(x) == 4) # [ ["blob", "abcd"], ["foo", "bar", "thing"] ]
```