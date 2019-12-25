---
title: digitize
tags: math,beginner
---

Converts a number to an array of digits.

Use `string(n)` to convert the number to a string, `split()` to convert to a character array.
Use `parse.()` to convert each element in the array to an `Int32`.

```jl
function digitize(n)
  return parse.(Int32, split(string(n), ""))
end
```

```jl
digitize(123) # [1, 2, 3]
```
