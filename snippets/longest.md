---
title: longest
tags: array,string,intermediate
---

Returns the longest element in args.

Use `length.()` to get the length of each element in `args`, get maximum length using `maximum()`.
Use `findfirst()` to get the longest item's index and return it from `args`.

```jl
function longest(args...)
  return args[findfirst(x -> length(x) == maximum(length.(args)), args)]
end
```

```jl
longest("foo", "bar", "thing", [1, 2, 3, 4, 5, 6]) # [1, 2, 3, 4, 5, 6]
```
