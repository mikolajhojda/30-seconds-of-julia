---
title: digitize
tags: math,array,beginner
---

Converts a number to an array of digits.

Use `split()` to split string based on a common seperator. 
Use `parse.()` to convert the type of an array (eg, Int32 to String).

```jl
function digitize(n)
  return parse.(Int32, split(string(n), ""))
end
```

```jl
digitize(123) # [1, 2, 3]
digitize(78910) # [7, 8, 9, 1, 0]
```
