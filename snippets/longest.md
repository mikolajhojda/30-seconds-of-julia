---
title: longest
tags: array,string,intermediate
---

Returns the longest String/Array of args.

Use `length.()` to get the length of each element in `args`, get maximum length using `maximum()`, then use `findfirst()` to get the longest items index. Then, access args at that index to return the longest item in `args`

```jl
function longest(args...)
  return args[findfirst(x -> length(x) == maximum(length.(args)), args)]
end
```

```jl
longest("foo", "bar", "thing", [1, 2, 3, 4, 5, 6]) # [1, 2, 3, 4, 5, 6]
```
