---
title: chunk
tags: array,intermediate
---

Chunks a list into smaller lists of a specified size.

Using array comprehension, `min()` and  `length()`

```jl
function chunk_arr(arr, n)
  return [arr[i:min(i + n - 1, end)] for i in 1:n:length(arr)]
end
```

```jl
chunk_arr([1,2,3,4,5],2) # [[1,2],[3,4],5]
chunk_arr([1, 2, 3, 4, 5, 6, 7, 8, 9], 4) # [[1, 2, 3, 4], [5, 6, 7, 8], [9]]
```
