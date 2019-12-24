---
title: bifurcate
tags: array,intermediate
---

Splits values into two groups. 
If an element in `filter` is `true`, the corresponding element in the collection belongs to the first group; otherwise, it belongs to the second group.

Use `findall()` with `filter` to get array indices that correspond to `true`.
Use those indices in a list comprehension to build the first group. 
Similarly, use `findall()` to get array indices that correspond to `false` and build the second group.

```jl
function bifurcate(array, filter)
  return [[array[i] for i in findall(x -> x == true, filter)], [array[i] for i in findall(x -> x == false, filter)]]
end
```

```jl
bifurcate(["beep", "boop", "foo", "bar"], [true, true, false, true]) # [ ['beep', 'boop', 'bar'], ['foo'] ]
```
