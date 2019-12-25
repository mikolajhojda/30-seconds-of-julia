---
title: flatten
tags: array,intermediate
---

Flattens an array of arrays once.

Use nested array comprehension to extract each value from sub-arrays in order.

```jl
function flatten(arr):
  return [x for y in arr for x in y]
end
```

```jl
flatten([[1,2,3,4],[5,6,7,8]]) # 8-element Array{Int64,1}: 1, 2, 3, 4, 5, 6, 7, 8,
```
